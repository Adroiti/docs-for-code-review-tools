Pattern: Use of `NaN` comparison

Issue: -

## Description

Used when an expression is compared to `NaN` values like `numpy.NaN` and `float('nan')`.

`NaN` (Not A Number) is a special entity that does not equal to any other entity, including itself.
Therefore a comparison `==` between any object and `NaN` will yield `False`. The correct way to check whether a variable is `NaN` would be using the is operator.