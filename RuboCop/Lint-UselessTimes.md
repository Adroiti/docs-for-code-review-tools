Pattern: Use of unnecessary `Integer#times`

Issue: -

## Description

This rule checks for uses of `Integer#times` that will never yield
(when the integer <= 0) or that will only ever yield once
(`1.times`).

This rule is marked as unsafe as `times` returns its receiver, which
is *usually* OK, but might change behavior.

## Examples

```ruby
# bad
-5.times { do_something }
0.times { do_something }
1.times { do_something  }
1.times { |i| do_something(i) }

# good
do_something
do_something(1)
```

## Further Reading

* [RuboCop - Lint/UselessTimes](https://docs.rubocop.org/rubocop/cops_lint.html#lintuselesstimes)
