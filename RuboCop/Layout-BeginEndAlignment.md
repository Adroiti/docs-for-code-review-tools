Pattern: Misaligned end keyword of `begin`

Issue: -

## Description

This rule checks whether the end keyword of `begin` is aligned properly.

Two modes are supported through the `EnforcedStyleAlignWith` configuration
parameter. If it's set to `start_of_line` (which is the default), the
`end` shall be aligned with the start of the line where the `begin`
keyword is. If it's set to `begin`, the `end` shall be aligned with the
`begin` keyword.

`Layout/EndAlignment` rule aligns with keywords (e.g. `if`, `while`, `case`)
by default. On the other hand, `||= begin` that this rule targets tends to
align with the start of the line, it defaults to `EnforcedStyleAlignWith: start_of_line`.
These style can be configured by each rule.

## Examples

#### EnforcedStyleAlignWith: start_of_line (default)

```ruby
# bad
foo ||= begin
          do_something
        end

# good
foo ||= begin
  do_something
end
```

#### EnforcedStyleAlignWith: begin

```ruby
# bad
foo ||= begin
  do_something
end

# good
foo ||= begin
          do_something
        end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyleAlignWith | `start_of_line` | `start_of_line`, `begin`
Severity | `warning` | String

## Further Reading

* [RuboCop - Layout/BeginEndAlignment](https://docs.rubocop.org/rubocop/cops_layout.html#layoutbeginendalignment)
