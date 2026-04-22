## `ScrollableRow / ScrollableColumn`
A scrollable container (a ScrollBar appears if the content doesn't fit).

### `ScrollableRow / ScrollableColumn` is a subclass of: `LayoutType`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `[(Align, NevuObject)]` | initial content. |
| `spacing` | `int | float` | distance between elements(default is 10). |
| `arrow_scroll_power` | `int` | scroll speed using arrow keys. |
| `wheel_scroll_power` | `int` | scroll speed using the mouse wheel. |
| `inverted_scrolling` | `bool` | invert scrolling(default is False). |
| `scrollbar_perc` | `NvVector2` | custom slider size in percentages(default is (0.05, 0.05)). |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject, align: Align` | adds item to the layout. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "ScrollableRow / ScrollableColumn example")

    menu = Menu(window, (100%vw, 100%vh))

    lbla = Label("A", [100, 50], single_instance = False)
    lblb = Label("B", [100, 50], single_instance = False)
    lblc = Label("C", [100, 50], single_instance = False)

    content = []
    for i in range(10):
        content.append((Align.LEFT, lbla))
        content.append((Align.CENTER, lblb))
        content.append((Align.RIGHT, lblc))

    layout = ScrollableColumn([100*vw, 100*vh], content = content)

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

    window = Window((500, 500), title = "ScrollableRow / ScrollableColumn example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    lbla = Label("A", [100, 50], single_instance = False)
    lblb = Label("B", [100, 50], single_instance = False)
    lblc = Label("C", [100, 50], single_instance = False)

    content = []
    for i in range(10):
        content.append((Align.LEFT, lbla))
        content.append((Align.CENTER, lblb))
        content.append((Align.RIGHT, lblc))

    layout = ScrollableColumn([100*vw, 100*vh], content = content)

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