Pattern: Inconsistent use of `ENV['HOME']`

Issue: -

## Description

Checks for consistent usage of `ENV['HOME']`. If nil is used as the second argument of `ENV.fetch`, it is treated as a bad case like `ENV[]`.

## Examples

```ruby
# bad
ENV['HOME']
ENV.fetch('HOME', nil)

# good
Dir.home

# good
ENV.fetch('HOME', default)
```

## Further Reading

* [RuboCop - Style/EnvHome](https://docs.rubocop.org/rubocop/cops_style.html#styleenvhome)
