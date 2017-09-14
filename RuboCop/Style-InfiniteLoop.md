Pattern: Use of `while`/`until` for infinite loop

Issue: -

## Description

This cop enforces to use `Kernel#loop` for infinite loops.

### Example

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

* [RuboCop - Style/InfiniteLoop](https://rubocop.readthedocs.io/en/latest/cops_style/#styleinfiniteloop)
* [https://github.com/bbatsov/ruby-style-guide#infinite-loop](https://github.com/bbatsov/ruby-style-guide#infinite-loop)
