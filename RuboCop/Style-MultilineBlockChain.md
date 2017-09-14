Pattern: Multiline block chain

Issue: -

## Description

This cop checks for chaining of a block after another block that spans
multiple lines.

### Example

```ruby
Thread.list.find_all do |t|
  t.alive?
end.map do |t|
  t.object_id
end
```

## Further Reading

* [RuboCop - Style/MultilineBlockChain](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultilineblockchain)
* [https://github.com/bbatsov/ruby-style-guide#single-line-blocks](https://github.com/bbatsov/ruby-style-guide#single-line-blocks)
