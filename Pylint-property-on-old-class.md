Pattern: Property on old class

Issue: -

## Description

Used when Pylint detect the use of the builtin "property" on an old style class while this is relying on new style classes features. This message can't be emitted when using Python >= 3.0.