Pattern: Nested percent literal

Issue: -

## Description

Within percent literals, nested percent literals do not function and may be unwanted in the result.

## Examples

```ruby
# bad

# The percent literal for nested_attributes is parsed as four tokens,
# yielding the array [:name, :content, :"%i[incorrectly", :"nested]"].
attributes = {
  valid_attributes: %i[name content],
  nested_attributes: %i[name content %i[incorrectly nested]]
}
```

## Further Reading

* [RuboCop - Lint/NestedPercentLiteral](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintnestedpercentliteral)
