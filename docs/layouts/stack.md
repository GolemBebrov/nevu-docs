## `StackColumn` / `StackRow`
### Arranges elements one after another vertically (Column) or horizontally (Row).
### Specific kwargs:
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `([Align, NevuObject])` | initial content. |
| `spacing` | `int | float` | distance between elements(default is 10). |

### Methods:
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, alignment: Align` | adds item to the end of the stack. |

### Use case:
```python
from nevu_ui import *
import pygame

pygame.init()

window = Window((500, 500), title = "Stack example")

menu = Menu(window, (100%vw, 100%vh))

stack = StackColumn(content = [
    (Align.LEFT, Label("A", (100, 50))),
    (Align.RIGHT, Label("B", (100, 50))),
])

menu.layout = stack

while True:
    window.begin_frame()
    window.update()
    menu.update()
    menu.draw()
    window.end_frame()
```