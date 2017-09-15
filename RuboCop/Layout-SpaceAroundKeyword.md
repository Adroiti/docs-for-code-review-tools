Pattern: Malformed space around keyword

Issue: -

## Description

Checks the spacing around the keywords.

### Example

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

* [RuboCop - Layout/SpaceAroundKeyword](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspacearoundkeyword)
