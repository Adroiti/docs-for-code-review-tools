Pattern: Use of mixed-case character range

Issue: -

## Description

Checks for mixed-case character ranges since they include likely unintended characters.

Offenses are registered for regexp character classes like `/[A-z]/` as well as range objects like `('A'..'z')`.

## Examples

```ruby
# bad
r = /[A-z]/

# good
r = /[A-Za-z]/
```

## Further Reading

* [RuboCop - Lint/MixedCaseRange](https://docs.rubocop.org/rubocop/cops_lint.html#lintmixedcaserange)
