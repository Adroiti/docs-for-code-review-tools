Pattern: Unused block argument

Issue: -

## Description

Use `_` to prefix unused block parameters and local variables. It's also acceptable to use just `_` (although it's a bit less descriptive). This convention is recognized by the Ruby interpreter and tools like RuboCop and will suppress their unused variable warnings.

## Examples

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

* [RuboCop - Lint/UnusedBlockArgument](https://docs.rubocop.org/rubocop/cops_lint.html#lintunusedblockargument)
* [https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars](https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars)
