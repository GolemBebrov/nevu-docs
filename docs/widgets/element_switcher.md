## `ElementSwitcher`
A widget that allows you to switch between elements.

### `ElementSwitcher` is a subclass of: `Widget`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `elements` | `list` | list of elements. |
| `on_content_change` | `Callable` | callback function when content is moved. |
| `current_index` | `int` | current element index(default is 0). |
| `arrow_width` | `int` | arrow width in pixels(default is 30). |
| `left_text` | `str` | left arrow text(default is '<'). |
| `right_text` | `str` | right arrow text(default is '>'). |
| `left_key` | `Keys` | left arrow key(default is None). |
| `right_key` | `Keys` | right arrow key(default is None). |
| `offset_perc` | `NvVector2` | button offset from border(default is NvVector2(2, 2)). |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `step` | `step: int` | how many elements to step(default is 1). |
| `move_to` | `id: int` | moves to the specified element. |
| `find` | `id: int` | finds element with specified id |
| `rfind` | `id: int` | finds element with specified id from the end. |
| `count` | `None` | returns number of elements. |
| `remove` | `id: int` | removes element with specified id. |
| `add_element` | `element: Element` | adds element to the end. |
| `next` | `None` | moves to the next element. |
| `previous` | `None` | moves to the previous element. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "ElementSwitcher example")

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = ElementSwitcher((100, 100), ["item1", "item2", (3, "id"), ("item_with_id", id)])

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

    window = Window((500, 500), title = "ElementSwitcher example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    layout = Grid([100%fillw, 100%fillh], x=3, y=3)

    widget = ElementSwitcher((100, 100), ["item1", "item2", (3, "id"), ("item_with_id", id)])

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