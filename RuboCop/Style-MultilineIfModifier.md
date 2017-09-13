Pattern: Style/MultilineIfModifier

Issue: -

## Description

Checks for uses of if/unless modifiers with multiple-lines bodies.

### Example

```ruby
# bad
{
  result: 'this should not happen'
} unless cond

# good
{ result: 'ok' } if cond
```

## Further Reading

* [RuboCop - Style/MultilineIfModifier](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultilineifmodifier)
* [https://github.com/bbatsov/ruby-style-guide#no-multiline-if-modifiers](https://github.com/bbatsov/ruby-style-guide#no-multiline-if-modifiers)
