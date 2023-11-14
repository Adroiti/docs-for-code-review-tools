Pattern: Use of single-line `do`…`​end`

Issue: -

## Description

Checks for single-line `do`…`​end` block.

## Examples

```ruby
# bad
foo do |arg| bar(arg) end

# good
foo do |arg|
  bar(arg)
end

# bad
->(arg) do bar(arg) end

# good
->(arg) { bar(arg) }
```

## Further Reading

* [RuboCop - Style/SingleLineDoEndBlock](https://docs.rubocop.org/rubocop/cops_style.html#stylesinglelinedoendblock)
