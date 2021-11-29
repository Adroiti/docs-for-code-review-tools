Pattern: Missing use of `Process.clock_gettime(Process::CLOCK_MONOTONIC)`

Issue: -

## Description

Identifies places where `Concurrent.monotonic_time` can be replaced by `Process.clock_gettime(Process::CLOCK_MONOTONIC)`.

### Examples

```ruby
# bad
Concurrent.monotonic_time

# good
Process.clock_gettime(Process::CLOCK_MONOTONIC)
```

## Further Reading

* [RuboCop - Performance/ConcurrentMonotonicTime](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceconcurrentmonotonictime)
