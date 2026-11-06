---
tags:
  - Python
  - Software Engineering
---

# 2026-11-06 — Attrs, Pydantic, or Python Data Classes?

## Resource watched

**Title:** [Attrs, Pydantic, or Python Data Classes?](https://www.youtube.com/watch?v=zN4VCb0LbQI)

**Type:** Video

## Summary and takeaways

**What are dataclasses?** "Data classes are just regular classes that are geared towards storing state, rather than containing a lot of logic. Every time you create a class that mostly consists of attributes, you make a data class." (great definition and explanation from [Stack Overflow](https://stackoverflow.com/a/47955313))

Python implementation `@dataclass` makes it easier to write such data classes by shortcutting a lot of boilerplate code.

Compare the starting code:

```python
# Source - https://stackoverflow.com/a/47955313
# Posted by Martijn Pieters, modified by community. See post 'Timeline' for change history
# Retrieved 2026-11-06, License - CC BY-SA 4.0

class InventoryItem:
    '''Class for keeping track of an item in inventory.'''
    name: str
    unit_price: float
    quantity_on_hand: int = 0

    def __init__(
            self, 
            name: str, 
            unit_price: float,
            quantity_on_hand: int = 0
        ) -> None:
        self.name = name
        self.unit_price = unit_price
        self.quantity_on_hand = quantity_on_hand

    def total_cost(self) -> float:
        return self.unit_price * self.quantity_on_hand
    
    def __repr__(self) -> str:
        return (
            'InventoryItem('
            f'name={self.name!r}, unit_price={self.unit_price!r}, '
            f'quantity_on_hand={self.quantity_on_hand!r})'
        )

    def __hash__(self) -> int:
        return hash((self.name, self.unit_price, self.quantity_on_hand))

    def __eq__(self, other) -> bool:
        if not isinstance(other, InventoryItem):
            return NotImplemented
        return (
            (self.name, self.unit_price, self.quantity_on_hand) == 
            (other.name, other.unit_price, other.quantity_on_hand))

```

vs with `@dataclass`

```python
# Source - https://stackoverflow.com/a/47955313
# Posted by Martijn Pieters, modified by community. See post 'Timeline' for change history
# Retrieved 2026-11-06, License - CC BY-SA 4.0

from dataclasses import dataclass

@dataclass(unsafe_hash=True)
class InventoryItem:
    '''Class for keeping track of an item in inventory.'''
    name: str
    unit_price: float
    quantity_on_hand: int = 0

    def total_cost(self) -> float:
        return self.unit_price * self.quantity_on_hand

```

**When do we need this?**

- Useful when your data class must be hashable.
- When class instances need to have defined relationships for comparisons and equality.
- To validate data types grouped together avoiding a lot of boilerplate code.

I.e. use it when you create re-usable tools and libraries. E.g. if your program has a large `config` structure with variables that define the workflow, it could be helpful to implement it as a dataclass. Side note: `attrs` is my personal favourite. 

**Which implementation to use?**

`dataclass` is a Python built-in, but there are also dedicated libraries such as [`attrs`](https://www.attrs.org/en/stable/) and [`pydantic`](https://pydantic.dev/docs/validation/latest/get-started/). They provide more useful features allowing flexible validation and class insatnce creation.

Rule of thumb: start by thinking with `dataclass` and if you hit a wall, examine using other libraries.

## Resources

- [general example of dataclass usage](https://github.com/pycollege/python-by-example/blob/main/lessons/dataclasses.md)
- [Python docs on @dataclass](https://docs.python.org/3/library/dataclasses.html)
- [`attrs` documentation](https://www.attrs.org/en/stable/). See [examples page](https://www.attrs.org/en/stable/examples.html) for a feature overview.
- [`pydantic`documentation](https://pydantic.dev/docs/validation/latest/get-started/) — Pydantic is first and foremost data validtion library

