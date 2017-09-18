Pattern: Improper arguments for `raise`/`fail`

Issue: -

## Description

This rule checks the args passed to `fail` and `raise`. For exploded
style (default), it recommends passing the exception class and message
to `raise`, rather than construct an instance of the error. It will
still allow passing just a message, or the construction of an error
with more than one argument.

The exploded style works identically, but with the addition that it
will also suggest constructing error objects when the exception is
passed multiple arguments.

## Examples

```ruby
# EnforcedStyle: exploded

# bad
raise StandardError.new("message")

# good
raise StandardError, "message"
fail "message"
raise MyCustomError.new(arg1, arg2, arg3)
raise MyKwArgError.new(key1: val1, key2: val2)
```
```ruby
# EnforcedStyle: compact

# bad
raise StandardError, "message"
raise RuntimeError, arg1, arg2, arg3

# good
raise StandardError.new("message")
raise MyCustomError.new(arg1, arg2, arg3)
fail "message"
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | exploded
SupportedStyles | compact, exploded

## Further Reading

* [RuboCop - Style/RaiseArgs](https://rubocop.readthedocs.io/en/latest/cops_style/#styleraiseargs)
* [https://github.com/bbatsov/ruby-style-guide#exception-class-messages](https://github.com/bbatsov/ruby-style-guide#exception-class-messages)
