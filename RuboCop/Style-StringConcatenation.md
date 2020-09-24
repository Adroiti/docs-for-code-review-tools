Pattern: Use of string concatenation instead of interpolation

Issue: -

## Description

This rule checks for places where string concatenation
can be replaced with string interpolation.

The rule can autocorrect simple cases but will skip autocorrecting
more complex cases where the resulting code would be harder to read.
In those cases, it might be useful to extract statements to local
variables or methods which you can then interpolate in a string.

## Examples

```ruby
# bad
email_with_name = user.name + ' <' + user.email + '>'

# good
email_with_name = "#{user.name} <#{user.email}>"
email_with_name = format('%s <%s>', user.name, user.email)
```

## Further Reading

* [RuboCop - Style/StringConcatenation](https://docs.rubocop.org/rubocop/cops_style.html#stylestringconcatenation)
* [The Ruby Style Guide](https://rubystyle.guide#string-interpolation)