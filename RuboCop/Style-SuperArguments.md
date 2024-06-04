Pattern: Redundant argument forwarding for `super`

Issue: -

## Description

Checks for redundant argument forwarding when calling `super` with arguments identical to the method definition.

## Examples

```ruby
# bad
def method(*args, **kwargs)
  super(*args, **kwargs)
end

# good - implicitly passing all arguments
def method(*args, **kwargs)
  super
end

# good - forwarding a subset of the arguments
def method(*args, **kwargs)
  super(*args)
end

# good - forwarding no arguments
def method(*args, **kwargs)
  super()
end
```

## Further Reading

* [RuboCop - Style/SuperArguments](https://docs.rubocop.org/rubocop/cops_style.html#stylesuperarguments)