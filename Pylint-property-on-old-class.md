Pattern: Property on old class

Issue: -

## Description

Used when Pylint detects the use of the builtin `property()` on an old style class while this is relying on new style class features. This message can't be emitted when using Python >= 3.0.
