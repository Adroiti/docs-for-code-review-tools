Pattern: Wrong keyword parameter order

Issue: -

## Description

This rule enforces that optional keyword parameters are placed at the
end of the parameters list.

This improves readability, because when looking through the source,
it is expected to find required parameters at the beginning of parameters list
and optional parameters at the end.

## Examples

```ruby
# bad
def some_method(first: false, second:, third: 10)
  # body omitted
end

# good
def some_method(second:, first: false, third: 10)
  # body omitted
end
```

## Further Reading

* [RuboCop - Style/KeywordParametersOrder](https://docs.rubocop.org/rubocop/cops_style.html#stylekeywordparametersorder)
* [The Ruby Style Guide](https://rubystyle.guide#keyword-parameters-order)