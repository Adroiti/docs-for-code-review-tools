Pattern: Model does not explicitly define `__unicode__`

Issue: -

## Description

Django models should implement a `__unicode__` method for string representation. A parent class of this model does, but ideally all models should be explicit.