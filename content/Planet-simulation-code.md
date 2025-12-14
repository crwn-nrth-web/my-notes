---
tags:
  - python
  - physics
  - 
draft: false
title: Planet-simulation-code
---
[[pygame-documentation]]

This project involved creating a two-dimensional simulation of planetary orbits using Python and Pygame, modeling motion under Newtonian gravity. The focus was on maintaining physical accuracy while addressing challenges in numerical stability, unit scaling, and visualization across the vastly different distances of the inner and outer Solar System.
- Orbits are restricted to two dimensions and assume near-circular, coplanar motion, neglecting orbital inclination and eccentricity.
##### Version 2 (Nov 22, 2025)
> When extending the simulation from the inner planets to include the outer planets (Jupiter, Saturn, Uranus, and Neptune), the project evolved from a straightforward orbital model into a more involved coding exercise that required extensive debugging and careful verification of physical accuracy. Addressing the issues that arose highlighted the importance of unit consistency, correct initial conditions, and thoughtful visualization choices.

Scaling challenges =
- **not seeing outer planets due to fixed scale** = The addition of outer planets introduced extreme disparities in spatial scale. With a fixed visual scale (e.g., 150 px/AU), Neptune’s orbit lies several thousand pixels off-screen in an 800×800 window. This revealed a fundamental limitation of fixed-scale visualizations when representing systems spanning multiple orders of magnitude.

To address this, a zoom factor was introduced that affects only the drawing stage, not the physics calculations. The physical positions remain unchanged, but the screen coordinates are computed using:
$$
\text{screen position} = (\text{physical position}) \times \text{scale} \times \text{zoom}
$$

- **planetary radii in true scale** = true size scaling of planetary radii is impractical. If drawn to scale: Most planets would be smaller than a pixel and the Sun would dominate the entire inner solar system. As a result, radii are treated as symbolic markers rather than literal sizes.
- **sun scaling** = The Sun requires additional handling due to its extreme size relative to planetary orbits. Initially, fixing the Sun at a constant pixel radius worked at a default zoom level but failed when zooming out, as the Sun remained visually dominant while planets shrank.

To resolve this, the Sun’s radius was scaled with zoom but clamped within reasonable bounds. This allows the Sun to:
- Appear large when zoomed in
- Shrink appropriately when zoomed out
- Remain visible without overlapping nearby orbits

DEBUGGING = clamping the sun's size relative to mercury's *position* caused the sun to pulsate in size over time because of Mercury moving along it's orbit
- By clamping the Sun’s size relative to Mercury’s orbital radius rather than its instantaneous position, the visual instability was eliminated.

```python cpp fold title:planet_simulation_version_2
import math
import pygame

# this is setting up the game window
pygame.init()
WIDTH, HEIGHT = 800, 800
WIN = pygame.display.set_mode((WIDTH, HEIGHT)) # this gives the pygame game surface
pygame.display.set_caption('Planet Simulation')
zoom = 1.0
zoom_speed = 1.1

WHITE = (255, 255, 255) #rgb for white
YELLOW = (255, 255, 0)
BLUE = (100, 149, 237)
RED = (188, 39, 50)
DARK_GREY = (80, 78, 81)
LIGHT_GREY = (211,211, 211)
ORANGE = (242, 125, 41)
PALE_YELLOW = (245, 239, 191)
GREY_BLUE = (99, 111, 176)
TEAL = (88, 195, 219)

FONT = pygame.font.SysFont("timesnewroman", 14)

class Planet:
    AU = 149.6e6 * 1000 # 1 AU = distance from the sun to the Earth in m
    G = 6.67428e-11
    scale = 150/AU # 1 AU = 100 pixels
    TIMESTEP = 3600*24 # 1 day (in sec)
    
    def __init__ (self, name, x, y, mass, radius, color):
        self.name = name
        self.x = x
        self.y = y
        self.mass = mass
        self. radius = radius
        self.color = color
        
        self.orbit = [] # this keeps tracks of all the points the planet travelled in order to draw the orbit
        self.sun = False # this identifies the sun in order to place the sun in the center
        self.distance_to_sun = 0
        
        self.vx = 0 
        self.vy = 0

    def draw(self, win, scale, zoom=1.0, inner_planet=None):
        scale_x = self.x * scale * zoom + WIDTH/2
        scale_y = self.y * scale * zoom + HEIGHT/2

        if len(self.orbit) > 2:
            updated_points = []
            for point in self.orbit:
                x_p, y_p = point
                x_up = x_p * scale * zoom + WIDTH /2   ## this makes the orbital points to scale
                y_up = y_p * scale * zoom + HEIGHT/2
                updated_points.append((x_up, y_up))
            pygame.draw.lines(win, self.color, False, updated_points, 2)

        if self.sun == True:
            if inner_planet:  # clamp to inner planet
                mercury_orbit_px = inner_planet.orbit_radius * scale * zoom
                radius_px = min(35 * zoom, mercury_orbit_px * 0.4)
            else:
                radius_px = 35 * zoom
                
            radius_px = max(10, radius_px)
        else:
            radius_px = (self.radius * 1000 / Planet.AU) * scale * zoom
            if radius_px < 2:
                radius_px = 2
            
        pygame.draw.circle(WIN, self.color, (scale_x , scale_y), radius_px)

        if not self.sun:
            distance_text = FONT.render(f"{self.name}", 1, WHITE)
            win.blit(distance_text, (scale_x - distance_text.get_width() - 5, scale_y - distance_text.get_height() // 2))


    def attraction(self, other): 
        ## x, y is in AU 
        other_x , other_y = other.x , other.y
        d_x = other.x - self.x
        d_y = other.y - self.y
        d = math.sqrt(d_x **2 + d_y **2)
        
        if other.sun:
            self.distance_to_sun = d
            
        f = (self.G * self.mass * other.mass)/ d**2
        theta = math.atan2(d_y, d_x)
        fx = math.cos(theta) * f
        fy = math.sin(theta) * f

        return fx , fy

    def update_position(self, planets):
        total_fx = total_fy = 0
        for planet in planets:
            if self == planet:
                continue

            fx, fy = self.attraction(planet)
            total_fx += fx
            total_fy += fy

        self.vx += total_fx / self.mass * self.TIMESTEP
        self.vy += total_fy / self.mass * self.TIMESTEP 

        self.x += self.vx * self.TIMESTEP
        self.y += self.vy * self.TIMESTEP

        self.orbit.append((self.x , self.y))
        

def main():
    run = True
    clock = pygame.time.Clock() ## this gives the frame rate (how many times the game is refreshing)
    scale = 150 / Planet.AU
    zoom_speed = 1.1

    sun = Planet("sun", 0,0, 1.98892e30, 699700, YELLOW)
    sun.sun = True
    
    mercury = Planet("mercury", 0.387*Planet.AU, 0, 3.33e23, 2440, DARK_GREY)
    mercury.orbit_radius = 0.387 * Planet.AU
    mercury.vy = 47.4e3
    
    venus = Planet ("venus", 0.723*Planet.AU, 0, 4.8685e24 , 6052, LIGHT_GREY)
    venus.vy = 35.02e3
    
    earth = Planet("earth", 1*Planet.AU, 0, 5.9742e24, 6371, BLUE)
    earth.vy = 29.783e3
    
    mars = Planet("mars", 1.524*Planet.AU, 0, 6.39e23, 3390, RED)
    mars.vy = 24.077e3

    jupiter = Planet("jupiter", 5.2*Planet.AU, 0, 1.9e27, 69911, ORANGE)
    jupiter.vy = 13.069e3

    saturn = Planet("saturn", 9.54*Planet.AU, 0, 5.685e26, 60268, PALE_YELLOW)
    saturn.vy = 9.68e3

    uranus = Planet("uranus", 19.2*Planet.AU, 0, 8.682e25, 25559, TEAL)
    uranus.vy = 6.8e3

    neptune = Planet("neptune", 30.06*Planet.AU, 0, 1.024e26, 24766, GREY_BLUE)
    neptune.vy = 5.43e3

    planets = [sun, mercury, venus, earth, mars, jupiter, saturn, uranus, neptune]
    
    while run:
        clock.tick(60)
        WIN.fill((0,0,0)) # this makes sure we do not see the old drawings of the planets as they move
    
        for event in pygame.event.get():     ### this makes a loop that allows the user to quit the game
            if event.type == pygame.QUIT:
                run = False

            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_EQUALS or event.key == pygame.K_KP_PLUS:
                    scale *= 2 # zoom in

                if event.key == pygame.K_MINUS or event.key == pygame.K_KP_MINUS:
                    scale /= zoom_speed  # zoom out
                
        for planet in planets:
            planet.update_position(planets)
            if planet.sun == True:
                planet.draw(WIN, scale, zoom, inner_planet=mercury)
            else:
                planet.draw(WIN, scale, zoom)

        note_text = FONT.render("To zoom in, press +    To zoom out, press -", 1, WHITE)
        WIN.blit(note_text, (10,10))
            
        pygame.display.update() 
            
    pygame.quit()

main()
```

<iframe src="https://trinket.io/embed/pygame/606d59a48b4e?outputOnly=true" width="100%" height="500" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
##### Version 1 (Nov 3, 2025) 
This version has the four inner planets with their approximate orbits based on the forces of gravitation from the sun and the other planets. 

Notes on the code =
- it sets up a simulation by defining a class (Planet) which includes functions to draw the planets and their orbits, calculate the total force of attraction on each planet, and update the position of the planet
- in order to set up the code, it required each planets mass, radius, distance from the sun (x), and vertical velocity (vy)
	- note: since this is an approximation, I used the Mean orbital speed of the planet as the vertical velocity 

Notes on the physics =

- Each planet starts on the positive x-axis relative to the Sun. To form an orbit rather than direct in-fall or escape, the initial velocity must be perpendicular to the radial displacement. Assigning velocity purely in the y-direction ensures that gravity acts as a centripetal force, continuously bending the planet’s path around the Sun. This directly reflects the classical mechanics description of circular and near-circular orbits.

```python cpp fold title:planet_simulation_version_1 
import math
import pygame

# this is setting up the game window
pygame.init()
WIDTH, HEIGHT = 800, 800
WIN = pygame.display.set_mode((WIDTH, HEIGHT)) # this gives the pygame game surface
pygame.display.set_caption('Planet Simulation')

WHITE = (255, 255, 255) #rgb for white
YELLOW = (255, 255, 0)
BLUE = (100, 149, 237)
RED = (188, 39, 50)
DARK_GREY = (80, 78, 81)
ORANGE = (242, 125, 41)
PALE_YELLOW = (245, 239, 191)
GREY_BLUE = (99, 111, 176)
TEAL = (88, 195, 219)

FONT = pygame.font.SysFont("timesnewroman", 14)

class Planet:
    AU = 149.6e6 * 1000 # 1 AU = distance from the sun to the Earth in m
    G = 6.67428e-11
    scale = 150/AU # 1 AU = 100 pixels
    TIMESTEP = 3600*24 # 1 day (in sec)
    
    def __init__ (self, x, y, mass, radius, color):
        self.x = x
        self.y = y
        self.mass = mass
        self. radius = radius
        self.color = color
        
        self.orbit = [] # this keeps tracks of all the points the planet travelled in order to draw the orbit
        self.sun = False # this identifies the sun in order to place the sun in the center
        self.distance_to_sun = 0
        
        self.vx = 0 
        self.vy = 0

    def draw(self, win):
        scale_x = self.x * self.scale + WIDTH/2
        scale_y = self.y * self.scale + HEIGHT/2

        if len(self.orbit) > 2:
            updated_points = []
            for point in self.orbit:
                x_p, y_p = point
                x_up = x_p * self.scale + WIDTH /2   ## this makes the orbital points to scale
                y_up = y_p * self.scale + HEIGHT/2
                updated_points.append((x_up, y_up))
            pygame.draw.lines(win, self.color, False, updated_points, 2)

        if self.sun == True:
            scale_radius = 35
        else:
            scale_radius = 0.25 * (self.radius)**(0.45)
            
        pygame.draw.circle(WIN, self.color, (scale_x , scale_y), scale_radius)

    def attraction(self, other): 
        ## x, y is in AU 
        other_x , other_y = other.x , other.y
        d_x = other.x - self.x
        d_y = other.y - self.y
        d = math.sqrt(d_x **2 + d_y **2)
        
        if other.sun:
            self.distance_to_sun = d
            
        f = (self.G * self.mass * other.mass)/ d**2
        theta = math.atan2(d_y, d_x)
        fx = math.cos(theta) * f
        fy = math.sin(theta) * f

        return fx , fy

    def update_position(self, planets):
        total_fx = total_fy = 0
        for planet in planets:
            if self == planet:
                continue

            fx, fy = self.attraction(planet)
            total_fx += fx
            total_fy += fy

        self.vx += total_fx / self.mass * self.TIMESTEP
        self.vy += total_fy / self.mass * self.TIMESTEP 

        self.x += self.vx * self.TIMESTEP
        self.y += self.vy * self.TIMESTEP

        self.orbit.append((self.x , self.y))


def main():
    run = True
    clock = pygame.time.Clock() 

    sun = Planet(0,0, 1.98892e30, 699700, YELLOW)
    sun.sun = True
    
    mercury = Planet(0.387*Planet.AU, 0, 3.33e23, 2440, DARK_GREY)
    mercury.vy = 47.4e3
    
    venus = Planet (0.723*Planet.AU, 0, 4.8685e24 , 6052, WHITE)
    venus.vy = 35.02e3
    
    earth = Planet(1*Planet.AU, 0, 5.9742e24, 6371, BLUE)
    earth.vy = 29.783e3
    
    mars = Planet(1.524*Planet.AU, 0, 6.39e23, 3390, RED)
    mars.vy = 24.077e3
    
    planets = [sun, mercury, venus, earth, mars]
    
    while run:
        clock.tick(60)
        WIN.fill((0,0,0)) # this makes sure we do not see the old drawings of the planets as they move
    
        for event in pygame.event.get():     
            if event.type == pygame.QUIT: ### this makes a loop that allows the user to quit the game
                run = False
                
        for planet in planets:
            planet.update_position(planets)
            planet.draw(WIN)
            
        pygame.display.update() 
            
    pygame.quit()

main()

```

<iframe src="https://trinket.io/embed/pygame/329c913eed21?outputOnly=true" width="100%" height="500" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>





