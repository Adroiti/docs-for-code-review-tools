Pattern: Redundant line break

Issue: -

## Description

Checks whether certain expressions, e.g. method calls, that could fit completely on a single line, are broken up into multiple lines unnecessarily.

## Examples

```ruby
# bad
foo(
  a,
  b
)

puts 'string that fits on ' \
     'a single line'

things
  .select { |thing| thing.cond? }
  .join('-')

# good
foo(a, b)

puts 'string that fits on a single line'

things.select { |thing| thing.cond? }.join('-')
```

## Further Reading

* [RuboCop - Layout/RedundantLineBreak](https://docs.rubocop.org/rubocop/cops_layout.html#layoutredundantlinebreak)