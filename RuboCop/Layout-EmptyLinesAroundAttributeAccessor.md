Pattern: Empty lines around attribute accessor

Issue: -

## Description

Checks for a newline after an attribute accessor or a group of them. `alias` syntax and `alias_method`, `public`, `protected`, and `private` methods are allowed by default. These are customizable with `AllowAliasSyntax` and `AllowedMethods` options.

## Examples

```ruby
# bad
attr_accessor :foo
def do_something
end

# good
attr_accessor :foo

def do_something
end

# good
attr_accessor :foo
attr_reader :bar
attr_writer :baz
attr :qux

def do_something
end
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundAttributeAccessor](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundattributeaccessor)