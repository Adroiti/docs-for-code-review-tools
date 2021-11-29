Pattern: Too many numbered parameters

Issue: -

## Description

This rule detects use of an excessive amount of numbered parameters in a
single block. Having too many numbered parameters can make code too
cryptic and hard to read.

The rule defaults to registering an offense if there is more than `1` numbered
parameter but this maximum can be configured by setting `Max`.

## Examples

#### Max: 1 (default)

```ruby
# bad
foo { _1.call(_2, _3, _4) }

# good
foo { do_something(_1) }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `1` | Integer

## Further Reading

* [RuboCop - Style/NumberedParametersLimit](https://docs.rubocop.org/rubocop/cops_style.html#stylenumberedparameterslimit)
