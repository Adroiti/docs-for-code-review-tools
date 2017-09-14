Pattern: Use of character literal

Issue: -

## Description

Checks for uses of the character literal `?x`. Since Ruby 1.9 it's basically redundant — `?x` would interpreted as `'x'` (a string with a single character in it).

### Example

```ruby
# bad
char = ?c

# good
char = 'c'
```

## Further Reading

* [RuboCop - Style/CharacterLiteral](https://rubocop.readthedocs.io/en/latest/cops_style/#stylecharacterliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-character-literals](https://github.com/bbatsov/ruby-style-guide#no-character-literals)
