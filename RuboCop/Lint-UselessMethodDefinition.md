Pattern: Unneeded method definition

Issue: -

## Description

This rule checks for useless method definitions, specifically: empty constructors
and methods just delegating to `super`.

This rule is marked as unsafe as it can trigger false positives for cases when
an empty constructor just overrides the parent constructor, which is bad anyway.

## Examples

```ruby
# bad
def initialize
  super
end

def method
  super
end

# good - with default arguments
def initialize(x = Object.new)
  super
end

# good
def initialize
  super
  initialize_internals
end

def method(*args)
  super(:extra_arg, *args)
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowComments | `true` | Boolean

## Further Reading

* [RuboCop - Lint/UselessMethodDefinition](https://docs.rubocop.org/rubocop/cops_lint.html#lintuselessmethoddefinition)
