Pattern: Missing format attribute

Issue: -

## Description

Used when a PEP 3101 format string uses an attribute specifier ({0.length}), but the argument passed for formatting doesn't have that attribute. This message can't be emitted when using Python < 2.7.