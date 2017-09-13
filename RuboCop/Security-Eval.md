Pattern: Security/Eval

Issue: -

## Description

This cop checks for the use of `Kernel#eval` and `Binding#eval`.

### Example

```ruby
# bad

eval(something)
binding.eval(something)
```

## Further Reading

* [RuboCop - Security/Eval](https://rubocop.readthedocs.io/en/latest/cops_security/#securityeval)
