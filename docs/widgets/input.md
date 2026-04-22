## `Input`
An InputBox widget.

### `Input` is a subclass of: `Widget`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `default` | `str` | default text. |
| `placefolder` | `str` | placeholder text when no text is present. |
| `on_change_function` | `Callable` | callback function when text is changed. |
| `is_active` | `bool` | can be clicked(default is True). |
| `multiple` | `bool` | can enter multiple lines(default is False). |
| `allow_paste` | `bool` | allow pasting text(default is True). |
| `max_characters` | `int / None` | set max characters(default is None). |
| `blacklist` | `list / str / None` | list of characters that can't be entered(default is None). |
| `whitelist` | `list / str / None` | list of characters that can be entered(default is None). |
| `padding` | `list / tuple` | padding in pixels(default is [0, 0, 0, 0]). |
| `cursor_width` | `int` | cursor width in pixels(default is 2). |

### Getters
| Name | ReturnType | Description |
| :--- | :--- | :--- |
| `text` | `str` | current entered text. |

### Setters
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `text` | `text` | overwrites current text with a new one. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "Input example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Input(size = (100, 100))

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

    window = Window((500, 500), title = "Input example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Input(size = (100, 100))

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