Pattern: Invalid style for variable number

Issue: -

## Description

This cop makes sure that all numbered variables use the configured style for their numbering.

### Example

```ruby
"EnforcedStyle => 'snake_case'"

# bad

variable1 = 1

# good

variable_1 = 1
```
```ruby
"EnforcedStyle => 'normalcase'"

# bad

variable_1 = 1

# good

variable1 = 1
```
```ruby
"EnforcedStyle => 'non_integer'"

#bad

variable1 = 1

variable_1 = 1

#good

variableone = 1

variable_one = 1
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | normalcase
SupportedStyles | snake_case, normalcase, non_integer

## Further Reading

* [RuboCop - Naming/VariableNumber](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingvariablenumber)
