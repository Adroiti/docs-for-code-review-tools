Pattern: Mixed named and numbered captures

Issue: -

## Description

Do not mix named captures and numbered captures in a Regexp literal because numbered capture is ignored if they’re mixed. Replace numbered captures with non-capturing groupings or named captures.

## Examples

```ruby
# bad
/(?<foo>FOO)(BAR)/

# good
/(?<foo>FOO)(?<bar>BAR)/

# good
/(?<foo>FOO)(?:BAR)/

# good
/(FOO)(BAR)/
```

## Further Reading

* [RuboCop - Lint/MixedRegexpCaptureTypes](https://docs.rubocop.org/rubocop/cops_lint.html#lintmixedregexpcapturetypes)
