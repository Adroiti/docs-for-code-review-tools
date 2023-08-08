Pattern: Missing newline for `do..end`

Issue: -

## Description

This rule checks whether the `end` statement of a `do..end` block is on its own line.

## Examples

```ruby
# bad
blah do |i|
  foo(i) end

# good
blah do |i|
  foo(i)
end

# bad
blah { |i|
  foo(i) }

# good
blah { |i|
  foo(i)
}
```

## Further Reading

* [RuboCop - Layout/BlockEndNewline](https://docs.rubocop.org/rubocop/cops_layout.html#layoutblockendnewline)
