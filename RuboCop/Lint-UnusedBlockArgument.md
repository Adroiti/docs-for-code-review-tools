Pattern: Unused block argument

Issue: -

## Description

This cop checks for unused block arguments.

### Example

```ruby
# bad

do_something do |used, unused|
  puts used
end

do_something do |bar|
  puts :foo
end

define_method(:foo) do |bar|
  puts :baz
end
```
```ruby
#good

do_something do |used, _unused|
  puts used
end

do_something do
  puts :foo
end

define_method(:foo) do |_bar|
  puts :baz
end
```

## Default configuration

Attribute | Value
--- | ---
IgnoreEmptyBlocks | true
AllowUnusedKeywordArguments | false

## Further Reading

* [RuboCop - Lint/UnusedBlockArgument](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunusedblockargument)
* [https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars](https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars)
