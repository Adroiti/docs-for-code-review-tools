Pattern: Improper use of `;`

Issue: -

## Description

This rule checks for multiple expressions placed on the same line.
It also checks for lines terminated with a semicolon.

## Examples

```ruby
# bad
puts 'foobar'; # superfluous semicolon

puts 'foo'; puts 'bar' # two expressions on the same line

# good
puts 'foobar'

puts 'foo'
puts 'bar'

puts 'foo', 'bar' # this applies to puts in particular
```

## Default configuration

Attribute | Value
--- | ---
AllowAsExpressionSeparator | false

## Further Reading

* [RuboCop - Style/Semicolon](https://docs.rubocop.org/rubocop/cops_style.html#stylesemicolon)
* [https://github.com/bbatsov/ruby-style-guide#no-semicolon](https://github.com/bbatsov/ruby-style-guide#no-semicolon)
