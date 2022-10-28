Pattern: Useless parent delegation

Issue: -

## Description

Used whenever we can detect that an overridden method is useless, relying on parent or `super()` delegation to do the same thing as another method from the MRO.
