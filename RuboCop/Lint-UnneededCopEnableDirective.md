Pattern: Unnecessary `rubocop:enable`

Issue: -

## Description

This rule detects instances of `rubocop:enable` comments that can be removed.

## Examples

```ruby
# bad
foo = 1
# rubocop:enable Metrics/LineLength

# good
foo = 1
```

## Further Reading

* [RuboCop - Lint/UnneededCopEnableDirective](https://docs.rubocop.org/rubocop/cops_lint.html#lintunneededcopenabledirective)
