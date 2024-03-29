Pattern: Missing documentation for class or module

Issue: -

## Description

This rule checks for missing top-level documentation of
classes and modules. Classes with no body are exempt from the
check and so are namespace modules - modules that have nothing in
their bodies except classes, other modules, or constant definitions.

The documentation requirement is annulled if the class or module has
a `#:nodoc:` comment next to it. Likewise, `#:nodoc: all` does the
same for all its children.

## Default configuration

Attribute | Value
--- | ---
Exclude | spec/\*\*/\*, test/\*\*/\*

## Further Reading

* [RuboCop - Style/Documentation](https://docs.rubocop.org/rubocop/cops_style.html#styledocumentation)
