Pattern: Missing cop enable directive

Issue: -

## Description

This rule checks that there is an `# rubocop:enable ...` statement
after a `# rubocop:disable ...` statement. This will prevent leaving
cop disables on wide ranges of code, that latter contributors to
a file wouldn't be aware of.

## Examples

```ruby
# Lint/MissingCopEnableDirective:
#   MaximumRangeSize: .inf

# good
# rubocop:disable Layout/SpaceAroundOperators
x= 0
# rubocop:enable Layout/SpaceAroundOperators
# y = 1
# EOF

# bad
# rubocop:disable Layout/SpaceAroundOperators
x= 0
# EOF
```
```ruby
# Lint/MissingCopEnableDirective:
#   MaximumRangeSize: 2

# good
# rubocop:disable Layout/SpaceAroundOperators
x= 0
# With the previous, there are 2 lines on which cop is disabled.
# rubocop:enable Layout/SpaceAroundOperators

# bad
# rubocop:disable Layout/SpaceAroundOperators
x= 0
x += 1
# Including this, that's 3 lines on which the cop is disabled.
# rubocop:enable Layout/SpaceAroundOperators
```

## Default configuration

Attribute | Value
--- | ---
MaximumRangeSize | `Infinity`

## Further Reading

* [RuboCop - Lint/MissingCopEnableDirective](https://docs.rubocop.org/rubocop/cops_lint.html#lintmissingcopenabledirective)
