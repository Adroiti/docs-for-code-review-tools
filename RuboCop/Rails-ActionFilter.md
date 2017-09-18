Pattern: Inconsistent use of action filter method

Issue: -

## Description

This rule enforces the consistent use of action filter methods.

The rule is configurable and can enforce the use of the older
`something_filter` methods or the newer `something_action` methods.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | action
SupportedStyles | action, filter
Include | app/controllers/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/ActionFilter](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsactionfilter)
