Pattern: Redundant `each`

Issue: -

## Description

Checks for redundant `each`.

## Examples

```ruby
# bad
array.each.each { |v| do_something(v) }

# good
array.each { |v| do_something(v) }

# bad
array.each.each_with_index { |v, i| do_something(v, i) }

# good
array.each.with_index { |v, i| do_something(v, i) }
array.each_with_index { |v, i| do_something(v, i) }

# bad
array.each.each_with_object { |v, o| do_something(v, o) }

# good
array.each.with_object { |v, o| do_something(v, o) }
array.each_with_object { |v, o| do_something(v, o) }
```

## Further Reading

* [RuboCop - Style/RedundantEach](https://docs.rubocop.org/rubocop/cops_style.html#styleredundanteach)
