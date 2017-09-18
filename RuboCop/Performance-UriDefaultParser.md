Pattern: Use of `URI::Parser.new` instead of `URI::DEFAULT_PARSER`

Issue: -

## Description

This rule identifies places where `URI::Parser.new` can be replaced by `URI::DEFAULT_PARSER`.

## Examples

```ruby
# bad
URI::Parser.new

# good
URI::DEFAULT_PARSER
```

## Further Reading

* [RuboCop - Performance/UriDefaultParser](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceuridefaultparser)
