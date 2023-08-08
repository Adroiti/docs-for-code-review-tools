Pattern: Use of `if`/`unless` in multi-line body

Issue: -

## Description

Checks for uses of `if`/`unless` modifiers with multi-line bodies.

## Examples

```ruby
# bad
{
  result: 'this should not happen'
} unless cond

# good
{ result: 'ok' } if cond
```

## Further Reading

* [RuboCop - Style/MultilineIfModifier](https://docs.rubocop.org/rubocop/cops_style.html#stylemultilineifmodifier)
* [https://github.com/bbatsov/ruby-style-guide#no-multiline-if-modifiers](https://github.com/bbatsov/ruby-style-guide#no-multiline-if-modifiers)
