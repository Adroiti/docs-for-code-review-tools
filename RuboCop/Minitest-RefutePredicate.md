Pattern: Missing use of `refute_predicate`

Issue: -

## Description

Enforces the test to use `refute_predicate` instead of using
`refute(obj.a_predicate_method?)`.

## Examples

``` ruby
# bad
refute(obj.one?)
refute(obj.one?, 'message')

# good
refute_predicate(obj, :one?)
refute_predicate(obj, :one?, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide/#refute-predicate>