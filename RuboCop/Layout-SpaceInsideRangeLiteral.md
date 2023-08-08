Pattern: Space inside range literal

Issue: -

## Description

Checks for spaces inside range literals.

## Examples

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

* [RuboCop - Layout/SpaceInsideRangeLiteral](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceinsiderangeliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-space-inside-range-literals](https://github.com/bbatsov/ruby-style-guide#no-space-inside-range-literals)
