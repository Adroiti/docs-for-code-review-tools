Pattern: Performance/RedundantBlockCall

Issue: -

## Description

This cop identifies the use of a `&block` parameter and `block.call`
where `yield` would do just as well.

### Example

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

* [RuboCop - Performance/RedundantBlockCall](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceredundantblockcall)
* [https://github.com/JuanitoFatas/fast-ruby#proccall-vs-yield-code](https://github.com/JuanitoFatas/fast-ruby#proccall-vs-yield-code)
