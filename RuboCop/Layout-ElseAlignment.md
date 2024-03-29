Pattern: Misaligned `else`

Issue: -

## Description

This rule checks the alignment of `else` keywords. Normally they should
be aligned with an `if`/`unless`/`while`/`until`/`begin`/`def` keyword, but there
are special cases when they should follow the same rules as the
alignment of end.

## Examples

```ruby
# bad
if something
  code
 else
  code
end

# bad
if something
  code
 elsif something
  code
end

# good
if something
  code
else
  code
end
```

## Further Reading

* [RuboCop - Layout/ElseAlignment](https://docs.rubocop.org/rubocop/cops_layout.html#layoutelsealignment)
