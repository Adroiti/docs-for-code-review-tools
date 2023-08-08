Pattern: Redundant `rubocop:enable` directive

Issue: -

## Description

This rule detects instances of `rubocop:enable` comments that can be
removed.

When comment enables all cops at once `rubocop:enable all`
that cop checks whether any cop was actually enabled.

## Examples

```ruby
# bad
foo = 1
# rubocop:enable Layout/LineLength

# good
foo = 1
```
```ruby
# bad
# rubocop:disable Style/StringLiterals
foo = "1"
# rubocop:enable Style/StringLiterals
baz
# rubocop:enable all

# good
# rubocop:disable Style/StringLiterals
foo = "1"
# rubocop:enable all
baz
```

## Further Reading

* [RuboCop - Lint/RedundantCopEnableDirective](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantcopenabledirective)
