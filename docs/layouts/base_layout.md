## `LayoutType`
A basic layout without any logic for arranging elements.

### `LayoutType` is a subclass of: `NevuObject`

### Specific kwargs
| Argument | Type | Description |
| :--- | :--- | :--- |
| `content` | `[NevuObject]` | initial content. |
| `borders` | `BorderConfig` | specific border configuration. |

### Methods
| Name | Kwargs | Description |
| :--- | :--- | :--- |
| `add_item` | `item: NevuObject` | adds item to the layout. |
| `add_floating_item` | `item: NevuObject` | adds floating item to the layout. |
| `get_item_by_id` | `id: int` | searching by id returns item or None. |
| `get_item_by_id_strict` | `id: int` | searching by id returns item or raises exception. |
| `add_items` | `Specific for layout` | only works in children. |

### Static methods
| Name | Kwargs | ReturnType | Description |
| :--- | :--- | :--- | :--- |
| `is_layout` | `NevuObject` | `bool` |  returns True if NevuObject is a LayoutType. |
| `is_widget` | `NevuObject` | `bool` |  returns True if NevuObject is a Widget. |

### Use case
=== "Pygame" 

    ```python
    from nevu_ui import *
    import pygame

    pygame.init()

    window = Window((500, 500), title = "LayoutType example")

    menu = Menu(window, (100%vw, 100%vh))

    lbla = Label("A", [100, 50], single_instance = True) #Single instance is important
    lblb = Label("B", [100, 50], single_instance = True) 

    lbla.coordinates = NvVector2(50, 50) #nvvector 2 in IMPORTANT !!!
    lblb.coordinates = NvVector2(200, 200)

    layout = LayoutType([100*vw, 100*vh])
    layout.add_floating_item(lbla)
    layout.add_floating_item(lblb)

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

    window = Window((500, 500), title = "LayoutType example", backend = Backend.RayLib)

    menu = Menu(window, (100%vw, 100%vh))

    lbla = Label("A", [100, 50], single_instance = True) #Single instance is important
    lblb = Label("B", [100, 50], single_instance = True) 

    lbla.coordinates = NvVector2(50, 50) #nvvector 2 in IMPORTANT !!!
    lblb.coordinates = NvVector2(200, 200)

    layout = LayoutType([100*vw, 100*vh])
    layout.add_floating_item(lbla)
    layout.add_floating_item(lblb)

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