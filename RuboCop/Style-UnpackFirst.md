Pattern: Missing use of `unpack1`

Issue: -

## Description

This rule checks for accessing the first element of `String#unpack` which can be replaced with the shorter method `unpack1`.

## Examples

```ruby
# bad
'foo'.unpack('h*').first
'foo'.unpack('h*')[0]
'foo'.unpack('h*').slice(0)
'foo'.unpack('h*').at(0)

# good
'foo'.unpack1('h*')
```

## Further Reading

* [RuboCop - Style/UnpackFirst](https://docs.rubocop.org/rubocop/cops_style.html#styleunpackfirst)
