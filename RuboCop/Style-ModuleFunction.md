Pattern: Use of `extend self` or `module_function`

Issue: -

## Description

This rule checks for use of `extend self` or `module_function` in a module.

## Examples

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

* [RuboCop - Style/ModuleFunction](https://docs.rubocop.org/rubocop/cops_style.html#stylemodulefunction)
* [https://github.com/bbatsov/ruby-style-guide#module-function](https://github.com/bbatsov/ruby-style-guide#module-function)
