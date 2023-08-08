Pattern: Use of `not`

Issue: -

## Description

This rule checks for uses of the keyword `not` instead of `!`.

## Examples

```ruby
# bad - parentheses are required because of op precedence
x = (not something)

# good
x = !something
```

## Further Reading

* [RuboCop - Style/Not](https://docs.rubocop.org/rubocop/cops_style.html#stylenot)
* [https://github.com/bbatsov/ruby-style-guide#bang-not-not](https://github.com/bbatsov/ruby-style-guide#bang-not-not)
