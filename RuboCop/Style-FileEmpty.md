Pattern: Missing use of `File.empty?('path/to/file')`

Issue: -

## Description

Prefer to use `File.empty?('path/to/file')` when checking if a file is empty.

## Examples

```ruby
# bad
File.zero?('path/to/file')
File.size('path/to/file') == 0
File.size('path/to/file') >= 0
File.size('path/to/file').zero?
File.read('path/to/file').empty?
File.binread('path/to/file') == ''
FileTest.zero?('path/to/file')

# good
File.empty?('path/to/file')
FileTest.empty?('path/to/file')
```

## Further Reading

* [RuboCop - Style/FileEmpty](https://docs.rubocop.org/rubocop/cops_style.html#stylefileempty)
