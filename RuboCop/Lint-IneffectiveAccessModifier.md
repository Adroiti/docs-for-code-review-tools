Pattern: Ineffective access modifier

Issue: -

## Description

This rule checks for `private` or `protected` access modifiers which are
applied to a singleton method. These access modifiers do not make
singleton methods private/protected. `private_class_method` can be
used for that.

## Examples

```ruby
# bad

class C
  private

  def self.method
    puts 'hi'
  end
end
```
```ruby
# good

class C
  def self.method
    puts 'hi'
  end

  private_class_method :method
end
```
```ruby
# good

class C
  class << self
    private

    def method
      puts 'hi'
    end
  end
end
```

## Further Reading

* [RuboCop - Lint/IneffectiveAccessModifier](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintineffectiveaccessmodifier)
