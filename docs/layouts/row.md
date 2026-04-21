## `Row`
### Specified `Grid` with locked x cells.
### Specific kwargs:
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `{int: NevuObject}` | initial content. |
| `row` / `x` | `int` | number of rows. |

### Methods:
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, x: int` | adds item into specified row, starting from 1. |

### Use case:
```python
from nevu_ui import *
import pygame

pygame.init()

window = Window((500, 500), title = "Row example")

menu = Menu(window, (100%vw, 100%vh))

row = Row((100%vw, 100%vh), x = 3, content = {
    2: Label("Text", (250, 100))
})

menu.layout = row

while True:
    window.begin_frame()
    window.update()
    menu.update()
    menu.draw()
    window.end_frame()
```