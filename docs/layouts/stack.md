## `StackRow / StackColumn`
A container for arranging elements one after another vertically (Column) or horizontally (Row).

### `StackRow / StackColumn` is a subclass of: `LayoutType`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `[(Align, NevuObject)]` | initial content. |
| `spacing` | `int | float` | distance between elements(default is 10). |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, alignment: Align` | adds item to the end of the stack. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "StackRow / StackColumn example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = StackColumn(content = [
        (Align.LEFT, Label("A", (100, 50))),
        (Align.RIGHT, Label("B", (100, 50))),
    ])

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

    window = Window((500, 500), title = "StackRow / StackColumn example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = StackColumn(content = [
        (Align.LEFT, Label("A", (100, 50))),
        (Align.RIGHT, Label("B", (100, 50))),
    ])

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