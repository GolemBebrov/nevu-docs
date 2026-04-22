## `ProgressBar`
An ordinary progress bar.

### `ProgressBar` is a subclass of: `Widget`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `min_value / min` | `int / float` | minimum value(default is 0). |
| `max_value / max` | `int / float` | maximum value(default is 100). |
| `value` | `int / float` | starting value. |
| `color_pair_role / role` | `PairColorRole` | color role for the bar(default is BACKGROUND). |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `set_progress_by_value` | `value: int / float` | sets progress by value. |

### Getters
| Name | ReturnType | Description |
| :--- | :--- | :--- |
| `progress` | `int / float` | current progress in percentage. |
| `value` | `int / float` | current value. |

### Setters
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `progress` | `value: int / float` | sets progress. |
| `value` | `value: int / float` | sets value. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "ProgressBar example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = ProgressBar(size = (100, 100), value = 50)

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

    window = Window((500, 500), title = "ProgressBar example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = ProgressBar(size = (100, 100), value = 50)

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