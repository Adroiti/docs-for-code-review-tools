Pattern: Ambiguous assignment

Issue: -

## Description

This rule checks for mistyped shorthand assignments.

## Examples

```ruby
# bad
x =- y
x =+ y
x =* y
x =! y

# good
x -= y # or x = -y
x += y # or x = +y
x *= y # or x = *y
x != y # or x = !y
```

## Further Reading

* [RuboCop - Lint/AmbiguousAssignment](https://docs.rubocop.org/rubocop/cops_lint.html#lintambiguousassignment)
