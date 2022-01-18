Pattern: Missing use of `File.(bin)write`

Issue: -

## Description

Favor `File.(bin)write` convenience methods.

## Examples

```ruby
## text mode
# bad
File.open(filename, 'w').write(content)
File.open(filename, 'w') do |f|
  f.write(content)
end

# good
File.write(filename, content)
```

## Further Reading

* [RuboCop - Style/FileWrite](https://docs.rubocop.org/rubocop/cops_style.html#stylefilewrite)
