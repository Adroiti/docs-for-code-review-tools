Pattern: Space inside range literal

Issue: -

## Description

Checks for spaces inside range literals.

### Example

```ruby
# bad
1 .. 3

# good
1..3

# bad
'a' .. 'z'

# good
'a'..'z'
```

## Further Reading

* [RuboCop - Layout/SpaceInsideRangeLiteral](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceinsiderangeliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-space-inside-range-literals](https://github.com/bbatsov/ruby-style-guide#no-space-inside-range-literals)
