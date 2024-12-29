
# functions

`pygame` functions:  

| function  | use             |
| --------- | --------------- |
| `.init()` | Initiate pygame |
|           |                 |
|           |                 |

`pygame.display` functions:

| function                      | use                                                 |
| ----------------------------- | --------------------------------------------------- |
| `.set_mode((length, height))` | Set height and length of window and get surface     |
| `.flip()`                     | Refresh the screen with updates                     |
| `.quit()`                     | Close the window                                    |
| `.set_icon(icon)`             | Window icon, where `icon = pygame.image.load(path)` |
| `.set_caption(window_title)`  | Set the window title                                |

`surface` functions:
```python
surface = pygame.display.set_mode((LENGTH, HEIGHT))
```

| function       | use               |
| -------------- | ----------------- |
| `.fill(color)` | set surface color |

`pygame.event` functions:

| function | use                   |
| -------- | --------------------- |
| `.get()` | Return all the events |
|          |                       |

`event` functions:
 
| function | use                              |
| -------- | -------------------------------- |
| `.type`  | type of event - e.g, `QUIT`, etc |
|          |                                  |

`pygame.time.clock()` functions:
- provides temporal control
- enables us to control frame rate.

| function            | use                                            |
| ------------------- | ---------------------------------------------- |
| `.tick(tick_speed)` | The game wont run higher than given tick_speed |
|                     |                                                |
