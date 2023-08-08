Pattern: Malformed class method definition

Issue: -

## Description

This rule enforces using `def self.method_name` or `class << self` to define class methods.

## Examples

#### EnforcedStyle: def_self (default)

```ruby
# bad
class SomeClass
  class << self
    attr_accessor :class_accessor

    def class_method
      # ...
    end
  end
end

# good
class SomeClass
  def self.class_method
    # ...
  end

  class << self
    attr_accessor :class_accessor
  end
end

# good - contains private method
class SomeClass
  class << self
    attr_accessor :class_accessor

    private

    def private_class_method
      # ...
    end
  end
end
```

#### EnforcedStyle: self_class

```ruby
# bad
class SomeClass
  def self.class_method
    # ...
  end
end

# good
class SomeClass
  class << self
    def class_method
      # ...
    end
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `def_self` | `def_self`, `self_class`

## Further Reading

* [RuboCop - Style/ClassMethodsDefinitions](https://docs.rubocop.org/rubocop/cops_style.html#styleclassmethodsdefinitions)
* [The Ruby Style Guide](https://rubystyle.guide#def-self-class-methods)