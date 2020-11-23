Pattern: Unnecessary `block_given?`

Issue: -

## Description

Identifies unnecessary use of a `block_given?` where explicit check of block argument would suffice.

## Examples

```ruby
# bad
def method(&block)
  do_something if block_given?
end

# good
def method(&block)
  do_something if block
end

# good - block is reassigned
def method(&block)
  block ||= -> { do_something }
  warn "Using default ..." unless block_given?
  # ...
end
```

## Further Reading

* [RuboCop - Performance/BlockGivenWithExplicitBlock](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceblockgivenwithexplicitblock)