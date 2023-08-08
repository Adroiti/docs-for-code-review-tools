Pattern: Use of options hash

Issue: -

## Description

This rule checks for options hashes and discourages them if the current Ruby version supports keyword arguments.

## Examples

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

* [RuboCop - Style/OptionHash](https://docs.rubocop.org/rubocop/cops_style.html#styleoptionhash)
