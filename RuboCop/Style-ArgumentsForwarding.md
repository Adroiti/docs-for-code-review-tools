Pattern: Missing use of arguments forwarding

Issue: -

## Description

In Ruby 2.7, arguments forwarding has been added.

This cop identifies places where `do_something(*args, &block)` can be replaced by `do_something(…​)`.


## Examples

```ruby
# bad
def foo(*args, &block)
  bar(*args, &block)
end

# bad
def foo(*args, **kwargs, &block)
  bar(*args, **kwargs, &block)
end

# good
def foo(...)
  bar(...)
end
```

## Further Reading

* [RuboCop - Style/ArgumentsForwarding](https://docs.rubocop.org/rubocop/cops_style.html#styleargumentsforwarding)
