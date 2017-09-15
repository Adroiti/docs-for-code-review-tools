Pattern: Use of `URI.regexp`

Issue: -

## Description

This cop identifies places where `URI.regexp` is obsolete and should not be used. Instead, use `URI::DEFAULT_PARSER.make_regexp`.

### Example

```ruby
# bad
URI.regexp('http://example.com')

# good
URI::DEFAULT_PARSER.make_regexp('http://example.com')
```

## Further Reading

* [RuboCop - Lint/UriRegexp](https://rubocop.readthedocs.io/en/latest/cops_lint/#linturiregexp)
