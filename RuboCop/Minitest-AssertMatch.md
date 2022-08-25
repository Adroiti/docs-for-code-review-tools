Pattern: Use of `assert(matcher.match(string))`

Issue: -

## Description

Enforces the test to use `assert_match` instead of using
`assert(matcher.match(string))`.

## Examples

``` ruby
# bad
assert(matcher.match(string))
assert(matcher.match(string), 'message')

# good
assert_match(regex, string)
assert_match(matcher, string, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#assert-match>