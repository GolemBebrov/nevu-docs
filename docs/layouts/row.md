## `Row`
specified `Grid` with locked y cells.

### `Row` is a subclass of: `Grid`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `{int: NevuObject}` | initial content. |
| `row / x` | `int` | number of rows. |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, x: int` | adds item into specified cell, starting from 1. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "Row example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Row((100%vw, 100%vh), x = 3, content = {
        2: Label("Text", (250, 100))
    })

    menu.layout = layout

    while True:
        window.begin_frame()
        window.update()
        menu.update()
        menu.draw()
        window.end_frame()

    ```

=== "Raylib"

    ```python
    from nevu_ui import *
    import pyray

    window = Window((500, 500), title = "Row example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Row((100%vw, 100%vh), x = 3, content = {
        2: Label("Text", (250, 100))
    })

    menu.layout = layout

    while True:
        window.begin_frame()
        window.update()
        menu.update()
        menu.draw()
        window.end_frame()

    ```


---
*<small>Created with GGen v1.0.9 for nevu_ui v0.7.5</small>*