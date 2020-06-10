Pattern: Redundant single-element character class

Issue: -

## Description

This rule checks for unnecessary single-element Regexp character classes.

## Examples

```ruby
# bad
r = /[x]/

# good
r = /x/

# bad
r = /[\s]/

# good
r = /\s/

# good
r = /[ab]/
```

## Further Reading

* [RuboCop - Style/RedundantRegexpCharacterClass](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantregexpcharacterclass)
