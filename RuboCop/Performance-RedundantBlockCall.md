Pattern: Redundant block call

Issue: -

## Description

This rule identifies the use of a `&block` parameter and `block.call` where `yield` would do just as well. In MRI Ruby, block arguments are converted to Procs, which incurs a heap allocation.

## Examples

```ruby
# bad
def method(&block)
  block.call
end
def another(&func)
  func.call 1, 2, 3
end

# good
def method
  yield
end
def another
  yield 1, 2, 3
end
```

## Further Reading

* [RuboCop - Performance/RedundantBlockCall](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantblockcall)
* [https://github.com/JuanitoFatas/fast-ruby#proccall-and-block-arguments-vs-yieldcode](https://github.com/JuanitoFatas/fast-ruby#proccall-and-block-arguments-vs-yieldcode)
