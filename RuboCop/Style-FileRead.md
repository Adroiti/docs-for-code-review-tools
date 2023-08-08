Pattern: Missing use of `File.(bin)read`

Issue: -

## Description

Favor `File.(bin)read` convenience methods.

## Examples

```ruby
## text mode
# bad
File.open(filename).read
File.open(filename, &:read)
File.open(filename) { |f| f.read }
File.open(filename) do |f|
  f.read
end
File.open(filename, 'r').read
File.open(filename, 'r', &:read)
File.open(filename, 'r') do |f|
  f.read
end

# good
File.read(filename)
```

## Further Reading

* [RuboCop - Style/FileRead](https://docs.rubocop.org/rubocop/cops_style.html#stylefileread)
