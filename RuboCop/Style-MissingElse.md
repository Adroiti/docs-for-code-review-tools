Pattern: Missing `else`

Issue: -

## Description

Checks for `if` expressions that do not have an `else` branch.

## Examples

```ruby
# bad
if condition
  statement
end
```
```ruby
# bad
case var
when condition
  statement
end
```
```ruby
# good
if condition
  statement
else
# the content of the else branch will be determined by Style/EmptyElse
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | both
SupportedStyles | if, case, both

## Further Reading

* [RuboCop - Style/MissingElse](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemissingelse)
