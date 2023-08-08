Pattern: Malformed `case` indentation

Issue: -

## Description

This rule checks how the `when`s of a `case` expression
are indented in relation to its `case` or `end` keyword.

It will register a separate offense for each misaligned `when`.

## Examples

```ruby
# If Layout/EndAlignment is set to keyword style (default)
# *case* and *end* should always be aligned to same depth,
# and therefore *when* should always be aligned to both -
# regardless of configuration.

# bad for all styles
case n
  when 0
    x * 2
  else
    y / 3
end

# good for all styles
case n
when 0
  x * 2
else
  y / 3
end
```
```ruby
# if EndAlignment is set to other style such as
# start_of_line (as shown below), then *when* alignment
# configuration does have an effect.

# EnforcedStyle: case (default)

# bad
a = case n
when 0
  x * 2
else
  y / 3
end

# good
a = case n
    when 0
      x * 2
    else
      y / 3
end

# EnforcedStyle: end

# bad
a = case n
    when 0
      x * 2
    else
      y / 3
end

# good
a = case n
when 0
  x * 2
else
  y / 3
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | case
SupportedStyles | case, end
IndentOneStep | false
IndentationWidth |

## Further Reading

* [RuboCop - Layout/CaseIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutcaseindentation)
* [https://github.com/bbatsov/ruby-style-guide#indent-when-to-case](https://github.com/bbatsov/ruby-style-guide#indent-when-to-case)
