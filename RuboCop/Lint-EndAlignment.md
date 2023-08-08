Pattern: Misaligned `end`

Issue: -

## Description

This rule checks whether the `end` keywords are aligned properly.

Three modes are supported through the `EnforcedStyleAlignWith`
configuration parameter:

If it's set to `keyword` (which is the default), the `end`
shall be aligned with the start of the keyword (if, class, etc.).

If it's set to `variable` the `end` shall be aligned with the
left-hand-side of the variable assignment, if there is one.

If it's set to `start_of_line`, the `end` shall be aligned with the
start of the line where the matching keyword appears.

## Examples

```ruby
# bad

variable = if true
    end
```
```ruby
# EnforcedStyleAlignWith: keyword (default)

# good

variable = if true
           end
```
```ruby
# EnforcedStyleAlignWith: variable

# good

variable = if true
end
```
```ruby
# EnforcedStyleAlignWith: start_of_line

# good

puts(if true
end)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleAlignWith | keyword
SupportedStylesAlignWith | keyword, variable, start_of_line

## Further Reading

* [RuboCop - Lint/EndAlignment](https://docs.rubocop.org/rubocop/cops_lint.html#lintendalignment)
