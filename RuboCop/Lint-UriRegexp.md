Pattern: Use of `URI.regexp`

Issue: -

## Description

This rule identifies places where `URI.regexp` is obsolete and should not be used. Instead, use `URI::DEFAULT_PARSER.make_regexp`.

## Examples

```ruby
# bad
URI.regexp('http://example.com')

# good
URI::DEFAULT_PARSER.make_regexp('http://example.com')
```

## Further Reading

* [RuboCop - Lint/UriRegexp](https://docs.rubocop.org/rubocop/cops_lint.html#linturiregexp)
