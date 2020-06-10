Pattern: Use of `bind(obj).call(args, …​)`

Issue: -

## Description

In Ruby 2.7, `UnboundMethod#bind_call` has been added.

This rule identifies places where `bind(obj).call(args, …​)` can be replaced by `bind_call(obj, args, …​)`.

The `bind_call(obj, args, …​)` method is faster than `bind(obj).call(args, …​)`.

### Examples

```ruby
# bad
umethod.bind(obj).call(foo, bar)
umethod.bind(obj).(foo, bar)

# good
umethod.bind_call(obj, foo, bar)
```

## Further Reading

* [RuboCop - Performance/BindCall](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancebindcall)
