
# Layouts

All Layouts accept base parameters: `size`, `style`, `content` (a list/dictionary of child elements).

---

## `StackColumn` / `StackRow`
### Arranges elements one after another vertically (Column) or horizontally (Row).
* **Specific kwargs:**
  * `spacing` (int | float): Distance between elements (default is 10).
* **Methods:**
  * `add_item(item: NevuObject, alignment: Align)` — Add an element with alignment.

---



---


```python
Row((300, 300), y = 3, content = {
    2: Label("Text", (250, 100))
})
```

---

## `ScrollableColumn` / `ScrollableRow`
### A scrollable container (a ScrollBar appears if the content doesn't fit).
* **Specific kwargs:**
  * `spacing` (int | float): Spacing between elements.
  * `arrow_scroll_power` (int): Scroll speed using arrow keys.
  * `wheel_scroll_power` (int): Scroll speed using the mouse wheel.
  * `inverted_scrolling` (bool): Invert scrolling.
  * `scrollbar_perc` (NvVector2): Custom slider size in percentages.
