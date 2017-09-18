Pattern: Nested method definition

Issue: -

## Description

This rule checks for nested method definitions.

## Examples

```ruby
# bad

# `bar` definition actually produces methods in the same scope
# as the outer `foo` method. Furthermore, the `bar` method
# will be redefined every time `foo` is invoked.
def foo
  def bar
  end
end
```
```ruby
# good

def foo
  bar = -> { puts 'hello' }
  bar.call
end
```
```ruby
# good

def foo
  self.class_eval do
    def bar
    end
  end
end

def foo
  self.module_exec do
    def bar
    end
  end
end
```
```ruby
# good

def foo
  class << self
    def bar
    end
  end
end
```

## Further Reading

* [RuboCop - Lint/NestedMethodDefinition](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintnestedmethoddefinition)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-methods](https://github.com/bbatsov/ruby-style-guide#no-nested-methods)
