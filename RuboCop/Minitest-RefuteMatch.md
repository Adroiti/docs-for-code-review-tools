Pattern: Missing use of `refute_match`

Issue: -

## Description

Enforces the test to use `refute_match` instead of using
`refute(matcher.match(string))`.

## Examples

``` ruby
# bad
refute(matcher.match(string))
refute(matcher.match(string), 'message')

# good
refute_match(matcher, string)
refute_match(matcher, string, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide#refute-match>