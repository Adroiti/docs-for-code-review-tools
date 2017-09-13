Pattern: Style/ModuleFunction

Issue: -

## Description

This cops checks for use of `extend self` or `module_function` in a
module.

Supported styles are: module_function, extend_self.

These offenses are not auto-corrected since there are different
implications to each approach.

### Example

```ruby
# Good if EnforcedStyle is module_function
module Test
  module_function
  ...
end

# Good if EnforcedStyle is extend_self
module Test
  extend self
  ...
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | module_function
SupportedStyles | module_function, extend_self

## Further Reading

* [RuboCop - Style/ModuleFunction](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemodulefunction)
* [https://github.com/bbatsov/ruby-style-guide#module-function](https://github.com/bbatsov/ruby-style-guide#module-function)
