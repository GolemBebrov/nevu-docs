## `RectCheckbox`
Simple checkbox. <small>:3 - easter egg 1.</small>

### `RectCheckbox` is a subclass of: `Widget`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `function / on_toggle` | `Callable` | callback function when checkbox is clicked. |
| `toggled` | `bool` | toggled state(default is False). |
| `active_rect_factor / active_factor` | `int / float` | how much of the rectangle is filled when toggled. |
| `checkbox_group` | `CheckBoxGroup / None` | adds checkbox to the specified group. |

### Getters
| Name | ReturnType | Description |
| :--- | :--- | :--- |
| `toggled` | `bool` | current toggled state. |

### Setters
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `toggled` | `value: bool` | sets toggled state. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "RectCheckbox example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = RectCheckBox(50)

    layout.add_item(widget, 2, 2)

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

    window = Window((500, 500), title = "RectCheckbox example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = RectCheckBox(50)

    layout.add_item(widget, 2, 2)

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