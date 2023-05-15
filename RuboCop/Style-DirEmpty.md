Pattern: Missing use of `Dir.empty?('path/to/dir')`

Issue: -

## Description

Prefer to use `Dir.empty?('path/to/dir')` when checking if a directory is empty.

## Examples

```ruby
# bad
Dir.entries('path/to/dir').size == 2
Dir.children('path/to/dir').empty?
Dir.children('path/to/dir').size == 0
Dir.each_child('path/to/dir').none?

# good
Dir.empty?('path/to/dir')
```

## Further Reading

* [RuboCop - Style/DirEmpty](https://docs.rubocop.org/rubocop/cops_style.html#styledirempty)
