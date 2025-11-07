---
tags:
  - python
  - physics
  - 
draft: true
title: Planet-simulation-code
---
 

```python
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

#        if not self.sun:
#            distance_text = FONT.render(f"{round(self.distance_to_sun/100, 1)} km", 1, WHITE)
#            win.blit(distance_text, (scale_x - distance_text.get_width()/2, scale_y - distance_text.get_height()/2))


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

    jupiter = Planet(5.2*Planet.AU, 0, 1.9e27, 69911, ORANGE)
    jupiter.vy = 13.069

    saturn = Planet(9.54*Planet.AU, 0, 5.685e26, 60268, PALE_YELLOW)
    saturn.vy = 9.68

    uranus = Planet(19.2*Planet.AU, 0, 8.682e25, 25559, TEAL)
    uranus.vy = 6.8

    neptune = Planet(30.06*Planet.AU, 0, 1.024e26, 24766, GREY_BLUE)
    neptune.vy = 5.43

    planets = [sun, mercury, venus, earth, mars]
    
    while run:
        clock.tick(60)
        WIN.fill((0,0,0)) # this makes sure we do not see the old drawings of the planets as they move
    
        for event in pygame.event.get():     ### this makes a loop that allows the user to quit the game
            if event.type == pygame.QUIT:
                run = False
                
        for planet in planets:
            planet.update_position(planets)
            planet.draw(WIN)
            
        pygame.display.update() 
            
    pygame.quit()

main()

```

<iframe src="https://trinket.io/embed/pygame/329c913eed21?outputOnly=true" width="100%" height="800" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>





