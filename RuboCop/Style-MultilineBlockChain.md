Pattern: Multi-line block chain

Issue: -

## Description

This rule checks for chaining of a block after another block that spans multiple lines.

## Examples

```ruby
names = %w[Bozhidar Steve Sarah]

# bad
names.each do |name|
  puts name
end

# good
names.each { |name| puts name }
```

## Further Reading

* [RuboCop - Style/MultilineBlockChain](https://docs.rubocop.org/rubocop/cops_style.html#stylemultilineblockchain)
* [https://github.com/bbatsov/ruby-style-guide#single-line-blocks](https://github.com/bbatsov/ruby-style-guide#single-line-blocks)
