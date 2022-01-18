Pattern: Missing use of `to_h`

Issue: -

## Description

Looks for uses of `map.to_h` or `collect.to_h` that could be written with just `to_h` in Ruby >= 2.6.

## Examples

```ruby
# bad
something.map { |v| [v, v * 2] }.to_h

# good
something.to_h { |v| [v, v * 2] }

# bad
{foo: bar}.collect { |k, v| [k.to_s, v.do_something] }.to_h

# good
{foo: bar}.to_h { |k, v| [k.to_s, v.do_something] }
```

## Further Reading

* [RuboCop - Style/MapToHash](https://docs.rubocop.org/rubocop/cops_style.html#stylemaptohash)
