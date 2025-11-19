---
title: pygame-documentation
draft: false
tags:
  - python
---
setting the game window =
```python
pygame.init()
WIDTH, HEIGHT = 800, 800
WIN = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption('    ')
```

setting up font =
```python
FONT = pygame.font.SysFont("timesnewroman", 14)
```

running the game =
```python
def main():
	run = True
	clock = pygame.time.Clock() ## this gives the frame rate (how many times the game is refreshing)
	
	while run:
		clock.tick(60)
	
		for event in pygame.event.get():
			if event.type == pygame.QUIT:
				run = False
	
		pygame.display.update()
	pygame.quit()
	
main()

```

