Pattern: Missing use of resource-cleanup version for method

Issue: -

## Description

This rule checks for cases when you could use a block
accepting version of a method that does automatic
resource cleanup.

## Examples

```ruby
# bad
f = File.open('file')

# good
File.open('file') do |f|
  ...
end
```

## Further Reading

* [RuboCop - Style/AutoResourceCleanup](https://docs.rubocop.org/rubocop/cops_style.html#styleautoresourcecleanup)
