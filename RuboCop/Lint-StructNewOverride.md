Pattern: Unexpected override of `Struct` built-in method

Issue: -

## Description

This rule checks unexpected overrides of the `Struct` built-in methods via `Struct.new`.

## Examples

```ruby
# bad
Bad = Struct.new(:members, :clone, :count)
b = Bad.new([], true, 1)
b.members #=> [] (overriding `Struct#members`)
b.clone #=> true (overriding `Object#clone`)
b.count #=> 1 (overriding `Enumerable#count`)

# good
Good = Struct.new(:id, :name)
g = Good.new(1, "foo")
g.members #=> [:id, :name]
g.clone #=> #<struct Good id=1, name="foo">
g.count #=> 2
```

## Further Reading

* [RuboCop - Lint/StructNewOverride](https://docs.rubocop.org/rubocop/cops_lint.html#lintstructnewoverride)
