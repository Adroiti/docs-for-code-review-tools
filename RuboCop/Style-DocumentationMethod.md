Pattern: Missing documentation for method 

Issue: -

## Description

This cop checks for missing documentation comment for public methods.
It can optionally be configured to also require documentation for
non-public methods.

### Example

```ruby
# bad

class Foo
  def bar
    puts baz
  end
end

module Foo
  def bar
    puts baz
  end
end

def foo.bar
  puts baz
end

# good

class Foo
  # Documentation
  def bar
    puts baz
  end
end

module Foo
  # Documentation
  def bar
    puts baz
  end
end

# Documentation
def foo.bar
  puts baz
end
```

## Default configuration

Attribute | Value
--- | ---
Exclude | spec/\*\*/\*, test/\*\*/\*
RequireForNonPublicMethods | false

## Further Reading

* [RuboCop - Style/DocumentationMethod](https://rubocop.readthedocs.io/en/latest/cops_style/#styledocumentationmethod)
