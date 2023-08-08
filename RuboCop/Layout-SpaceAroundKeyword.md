Pattern: Malformed space around keyword

Issue: -

## Description

Checks the spacing around the keywords.

## Examples

```ruby
# bad
something 'test'do|x|
end

while(something)
end

something = 123if test

# good
something 'test' do |x|
end

while (something)
end

something = 123 if test
```

## Further Reading

* [RuboCop - Layout/SpaceAroundKeyword](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacearoundkeyword)
