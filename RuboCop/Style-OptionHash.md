Pattern: Option hash

Issue: -

## Description

This cop checks for options hashes and discourages them if the
current Ruby version supports keyword arguments.

### Example

```ruby
Instead of:

def fry(options = {})
  temperature = options.fetch(:temperature, 300)
  ...
end

Prefer:

def fry(temperature: 300)
  ...
end
```

## Default configuration

Attribute | Value
--- | ---
SuspiciousParamNames | options, opts, args, params, parameters

## Further Reading

* [RuboCop - Style/OptionHash](https://rubocop.readthedocs.io/en/latest/cops_style/#styleoptionhash)
