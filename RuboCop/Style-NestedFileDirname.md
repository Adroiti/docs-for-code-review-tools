Pattern: Use of nested `File.dirname`

Issue: -

## Description

This rule checks for nested `File.dirname`. It replaces nested `File.dirname` with the level argument introduced in Ruby 3.1.

## Examples

```ruby
# bad
File.dirname(File.dirname(path))

# good
File.dirname(path, 2)
```

## Further Reading

* [RuboCop - Style/NestedFileDirname](https://docs.rubocop.org/rubocop/cops_style.html#stylenestedfiledirname)
