Pattern: Duplicate element in Regexp character class

Issue: -

## Description

Checks for duplicate elements in Regexp character classes.

## Examples

```ruby
# bad
r = /[xyx]/

# bad
r = /[0-9x0-9]/

# good
r = /[xy]/

# good
r = /[0-9x]/
```

## Further Reading

* [RuboCop - Lint/DuplicateRegexpCharacterClassElement](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicateregexpcharacterclasselement)
