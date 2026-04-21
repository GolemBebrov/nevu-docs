## `Column`
### Specified `Grid` with locked y cells.
### Specific kwargs:
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `{int: NevuObject}` | initial content. |
| `column` / `y` | `int` | number of columns. |

### Methods:
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, y: int` | adds item into specified column, starting from 1. |

### Use case:
```python
from nevu_ui import *
import pygame

pygame.init()

window = Window((500, 500), title = "Column example")

menu = Menu(window, (100%vw, 100%vh))

column = Column((100%vw, 100%vh), y = 3, content = {
    2: Label("Text", (250, 100))
})

menu.layout = column

while True:
    window.begin_frame()
    window.update()
    menu.update()
    menu.draw()
    window.end_frame()
```