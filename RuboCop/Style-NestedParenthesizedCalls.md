Pattern: Nested method call without parentheses

Issue: -

## Description

This rule checks for unparenthesized method calls in the argument list of a parenthesized method call.

## Examples

```ruby
# good
method1(method2(arg), method3(arg))

# bad
method1(method2 arg, method3, arg)
```

## Default configuration

Attribute | Value
--- | ---
Whitelist | be, be_a, be_an, be_between, be_falsey, be_kind_of, be_instance_of, be_truthy, be_within, eq, eql, end_with, include, match, raise_error, respond_to, start_with

## Further Reading

* [RuboCop - Style/NestedParenthesizedCalls](https://docs.rubocop.org/rubocop/cops_style.html#stylenestedparenthesizedcalls)
