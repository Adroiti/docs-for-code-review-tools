Pattern: Use of `__unicode__` method on model

Issue: -

## Description

Django models should not implement a `__unicode__` method for string representation when using _Python3_.
