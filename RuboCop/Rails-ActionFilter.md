Pattern: Rails/ActionFilter

Issue: -

## Description

This cop enforces the consistent use of action filter methods.

The cop is configurable and can enforce the use of the older
something_filter methods or the newer something_action methods.

If the TargetRailsVersion is set to less than 4.0, the cop will enforce
the use of filter methods.

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | action
SupportedStyles | action, filter
Include | app/controllers/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/ActionFilter](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsactionfilter)
