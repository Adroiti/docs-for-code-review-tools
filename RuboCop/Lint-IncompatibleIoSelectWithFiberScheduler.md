Pattern: Use of incompatible `IO.select` with Fiber Scheduler

Issue: -

## Description

This rule checks for `IO.select` that is incompatible with Fiber Scheduler since Ruby 3.0.

## Examples

```ruby
# bad
IO.select([io], [], [], timeout)

# good
io.wait_readable(timeout)

# bad
IO.select([], [io], [], timeout)

# good
io.wait_writable(timeout)
```

## Further Reading

* [RuboCop - Lint/IncompatibleIoSelectWithFiberScheduler](https://docs.rubocop.org/rubocop/cops_lint.html#lintincompatibleioselectwithfiberscheduler)
