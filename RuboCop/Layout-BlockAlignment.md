Pattern: Misaligned `end` in block

Issue: -

## Description

This rule checks whether the `end` keywords are aligned properly for `do..end` blocks.

Three modes are supported through the `EnforcedStyleAlignWith`
configuration parameter:

`start_of_block` : the `end` shall be aligned with the
start of the line where the `do` appeared.

`start_of_line` : the `end` shall be aligned with the
start of the line where the expression started.

`either` (which is the default) : the `end` is allowed to be in either location.

## Examples

```ruby
# bad

foo.bar
   .each do
     baz
       end
```
```ruby
# EnforcedStyleAlignWith: either (default)

# good

variable = lambda do |i|
  i
end
```
```ruby
# EnforcedStyleAlignWith: start_of_block

# good

foo.bar
  .each do
     baz
   end
```
```ruby
# EnforcedStyleAlignWith: start_of_line

# good

foo.bar
  .each do
     baz
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleAlignWith | either
SupportedStylesAlignWith | either, start_of_block, start_of_line

## Further Reading

* [RuboCop - Lint/BlockAlignment](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintblockalignment)
