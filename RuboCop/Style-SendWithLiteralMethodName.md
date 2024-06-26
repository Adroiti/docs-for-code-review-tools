Pattern: Use of `public_send` with literal argument

Issue: -

## Description

Detects the use of the `public_send` method with a literal method name argument. Since the `send` method can be used to call private methods, by default, only the `public_send` method is detected.

## Examples

```ruby
# bad
obj.public_send(:method_name)
obj.public_send('method_name')

# good
obj.method_name
```

## Further Reading

* [RuboCop - Style/SendWithLiteralMethodName](https://docs.rubocop.org/rubocop/cops_style.html#stylesendwithliteralmethodname)