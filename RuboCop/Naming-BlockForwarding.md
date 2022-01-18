Pattern: Missing use of block forwarding

Issue: -

## Description

In Ruby 3.1, anonymous block forwarding has been added.

This rule identifies places where `do_something(&block)` can be replaced by `do_something(&)`.

It also supports the opposite style by alternative explicit option.


## Examples

```ruby
# bad
def foo(&block)
  bar(&block)
end

# good
def foo(&)
  bar(&)
end
```

## Further Reading

* [RuboCop - Naming/BlockForwarding](https://docs.rubocop.org/rubocop/cops_naming.html#namingblockforwarding)