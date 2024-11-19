Pattern: Too many positional arguments

Issue: -

## Description

Used when a function has too many positional arguments.

Example of **incorrect** code:

```python
# +1: [too-many-positional-arguments]
def calculate_drag_force(velocity, area, density, drag_coefficient):
    """Each argument is positional-or-keyword unless a `/` or `*` is present."""
    return 0.5 * drag_coefficient * density * area * velocity**2


drag_force = calculate_drag_force(30, 2.5, 1.225, 0.47)
```

Example of **correct** code:

```python
def calculate_drag_force(*, velocity, area, density, drag_coefficient):
    """This function is 'Keyword only' for all args due to the '*'."""
    return 0.5 * drag_coefficient * density * area * velocity**2


# This is now impossible to do and will raise a TypeError:
# drag_force = calculate_drag_force(30, 2.5, 1.225, 0.47)
#              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
# TypeError: calculate_drag_force() takes 0 positional arguments but 4 were given

# And this is the only way to call 'calculate_drag_force'
drag_force = calculate_drag_force(
    velocity=30, area=2.5, density=1.225, drag_coefficient=0.47
)
```
