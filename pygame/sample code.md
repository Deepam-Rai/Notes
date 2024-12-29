
```python
import pygame  
from constants import *  
  
pygame.init()  
pygame.display.set_caption(WIN_CAPTION)  
screen = pygame.display.set_mode((WIN_LENGTH, WIN_HEIGHT))  
screen.fill(WIN_COLOR)  
  
clock = pygame.time.Clock()  
running = True  
while running:  
    for event in pygame.event.get():  
        if event.type == pygame.QUIT:  
            running = False  
    pygame.display.flip()  
    clock.tick(CLOCK_TICK)  
  
pygame.display.quit()
```

