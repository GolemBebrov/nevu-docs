## `Grid`
A rigid grid. Elements are positioned by cell coordinates.
### Specific kwargs:
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `{(int, int): NevuObject}` | initial content. |
| `row` / `x` | `int` | number of rows. |
| `column` / `y` | `int` | number of columns. |

### Methods:
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, x: int, y: int` | adds item into specified cell, starting from 1. |

### Use case:
```python
from nevu_ui import *
import pygame

pygame.init()

window = Window((500, 500), title = "Grid example")

menu = Menu(window, (100%vw, 100%vh))

grid = Grid((100%vw, 100%vh), x = 3,  y = 3, content = {
    (2, 2): Label("Text", (250, 100))
})

menu.layout = grid

while True:
    window.begin_frame()
    window.update()
    menu.update()
    menu.draw()
    window.end_frame()
```