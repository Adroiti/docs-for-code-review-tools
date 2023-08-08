Pattern: Misused `String#split`

Issue: -

## Description

Checks for uses of `String#split` with empty string or regexp literal argument.

This rule is marked as unsafe. But probably it’s quite unlikely that some other class would define a split method that takes exactly the same arguments.

## Examples

```ruby
# bad
string.split(//)
string.split('')

# good
string.chars
```

## Further Reading

* [RuboCop - Style/StringChars](https://docs.rubocop.org/rubocop/cops_style.html#stylestringchars)