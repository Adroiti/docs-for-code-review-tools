Pattern: Missing use of `assert_silent`

Issue: -

## Description

Enforces the test to use `assert_silent { ... }` instead of using
`assert_output('', '') { ... }`.

## Examples

``` ruby
# bad
assert_output('', '') { puts object.do_something }

# good
assert_silent { puts object.do_something }
```

## Further Reading

- <https://github.com/rubocop/minitest-style-guide#assert-silent>