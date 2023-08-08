Pattern: Missing use of keyword argument

Issue: -

## Description

This rule checks for places where keyword arguments can be used instead of boolean arguments when defining methods.

## Examples

```ruby
# bad
def some_method(bar = false)
  puts bar
end

# bad - common hack before keyword args were introduced
def some_method(options = {})
  bar = options.fetch(:bar, false)
  puts bar
end

# good
def some_method(bar: false)
  puts bar
end
```

## Further Reading

* [RuboCop - Style/OptionalBooleanParameter](https://docs.rubocop.org/rubocop/cops_style.html#styleoptionalbooleanparameter)
* [The Ruby Style Guide](https://rubystyle.guide#boolean-keyword-arguments)