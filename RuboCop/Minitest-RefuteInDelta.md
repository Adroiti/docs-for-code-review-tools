Pattern: Missing use of `refute_in_delta`

Issue: -

## Description

Enforces the test to use `refute_in_delta` instead of using
`refute_equal` to compare floats.

## Examples

``` ruby
# bad
refute_equal(0.2, actual)
refute_equal(0.2, actual, 'message')

# good
refute_in_delta(0.2, actual)
refute_in_delta(0.2, actual, 0.001, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide/#refute-in-delta>