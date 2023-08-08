Pattern: Misaligned first method parameter

Issue: -

## Description

Checks the indentation of the first parameter in a method call.

## Examples

```ruby
# bad
def some_method(
first_param,
second_param)
  123
end
```
#### EnforcedStyle: consistent (default)

```ruby
# The first parameter should always be indented one step more than the
# preceding line.

# good
def some_method(
  first_param,
second_param)
  123
end
```
#### EnforcedStyle: align_parentheses

```ruby
# The first parameter should always be indented one step more than the
# opening parenthesis.

# good
def some_method(
                 first_param,
second_param)
  123
end
```

## Configurable attributes

Name | Default value
--- | ---
EnforcedStyle | `consistent`
IndentationWidth | `<none>`

## Further Reading

* [RuboCop - Layout/IndentFirstParameter](https://docs.rubocop.org/rubocop/cops_layout.html#layoutindentfirstparameter)
