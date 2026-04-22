## `Slider`
Complex widget containing `ProgressBar` with possibility to drag it.

### `Slider` is a subclass of: `Widget`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `start` | `int / float` | starting value(default is 0). |
| `end` | `int / float` | ending value(default is 100). |
| `step` | `int / float` | step to change value(default is 1). |
| `current_value` | `int / float` | current value(default is 0). |
| `progress_style` | `Style / None` | progress bar style(default is None). |
| `padding_x` | `int` | text x padding in pixels(default is 0). |
| `padding_y` | `int` | text y padding in pixels(default is 0). |
| `tuple_role` | `TupleColorRole` | color role for the text(default is INVERSE_PRIMARY). |
| `bar_pair_role` | `PairColorRole` | color role for the bar(default is BACKGROUND). |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "Slider example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Slider(size = (100, 100))

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

    window = Window((500, 500), title = "Slider example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = Slider(size = (100, 100))

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