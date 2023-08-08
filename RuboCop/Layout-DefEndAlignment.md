Pattern: Misaligned `end` in method

Issue: -

## Description

This rule checks whether the `end` keywords of method definitions are aligned properly.

Two modes are supported through the EnforcedStyleAlignWith configuration
parameter. If it's set to `start_of_line` (which is the default), the
`end` shall be aligned with the start of the line where the `def`
keyword is. If it's set to `def`, the `end` shall be aligned with the
`def` keyword.

## Examples

```ruby
# bad

private def foo
            end
```
```ruby
# EnforcedStyleAlignWith: start_of_line (default)

# good

private def foo
end
```
```ruby
# EnforcedStyleAlignWith: def

# good

private def foo
        end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleAlignWith | start_of_line
SupportedStylesAlignWith | start_of_line, def

## Further Reading

* [RuboCop - Lint/DefEndAlignment](https://docs.rubocop.org/rubocop/cops_lint.html#lintdefendalignment)
