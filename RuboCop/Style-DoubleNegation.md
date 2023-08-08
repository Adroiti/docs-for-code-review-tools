Pattern: Use of `!!`

Issue: -

## Description

This rule checks for uses of double negation (`!!`) to convert something
to a boolean value. As this is both cryptic and usually redundant, it
should be avoided.

Please note that when something is a boolean value `!!something` and `!something.nil?` are not the same thing. As you're unlikely to write code that can accept values of any type this is rarely a problem in practice.

## Examples

```ruby
# bad
!!something

# good
!something.nil?
```

## Further Reading

* [RuboCop - Style/DoubleNegation](https://docs.rubocop.org/rubocop/cops_style.html#styledoublenegation)
* [https://github.com/bbatsov/ruby-style-guide#no-bang-bang](https://github.com/bbatsov/ruby-style-guide#no-bang-bang)
