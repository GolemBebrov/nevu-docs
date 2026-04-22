## `Widget`
A base widget, only drawing is implemented.

### `Widget` is a subclass of: `NevuObject`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `alt` | `bool` | swap borders and content colors(default is False). |
| `clickable` | `bool` | can be visually clicked(default is True). |
| `hoverable` | `bool` | can be visually hovered(default is True). |
| `fancy_click_style` | `bool` | change alt when clicked(default is False). |
| `inline` | `bool` | if True, will request surface to be set manually. |
| `font_role` | `PairColorRole` | font color role(default is INVERSE_SURFACE). |
| `_draw_borders` | `bool` | if False, renderer won`t draw borders(default is True). |
| `_draw_content` | `bool` | if False, renderer won`t draw content(default is True). |
| `ripple_effect` | `bool` | enable ripple effect(RAYLIB only, default is False). |
| `animate_color_change` | `bool` | animate color change(RAYLIB only, default is False). |
| `override_color` | `Color` | overrides `Widget`'s bgcolor (default is None). |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `clear_texture` | `None` | clears texture, use only in SDL mode |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "Widget example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Widget(size = (100, 100))

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

    window = Window((500, 500), title = "Widget example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Widget(size = (100, 100))

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