Pattern: Invalid accessor method name

Issue: -

## Description

This rule makes sure that accessor methods are named properly.

## Examples

```ruby
# bad
def set_attribute(value) ...

# good
def attribute=(value)

# bad
def get_attribute ...

# good
def attribute ...
```

## Further Reading

* [RuboCop - Naming/AccessorMethodName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingaccessormethodname)
* [https://github.com/bbatsov/ruby-style-guide#accessor_mutator_method_names](https://github.com/bbatsov/ruby-style-guide#accessor_mutator_method_names)
