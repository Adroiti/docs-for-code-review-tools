Pattern: Use of `while`/`until` for infinite loop

Issue: -

## Description

This rule enforces to use `Kernel#loop` for infinite loops.

## Examples

```ruby
# bad
while true
  work
end

# good
loop do
  work
end
```

## Further Reading

* [RuboCop - Style/InfiniteLoop](https://docs.rubocop.org/rubocop/cops_style.html#styleinfiniteloop)
* [https://github.com/bbatsov/ruby-style-guide#infinite-loop](https://github.com/bbatsov/ruby-style-guide#infinite-loop)
