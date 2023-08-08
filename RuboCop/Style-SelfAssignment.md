Pattern: Missing use of `%s=`

Issue: -

## Description

This rule enforces the use the shorthand for self-assignment.

## Examples

```ruby
# bad
x = x + 1

# good
x += 1
```

## Further Reading

* [RuboCop - Style/SelfAssignment](https://docs.rubocop.org/rubocop/cops_style.html#styleselfassignment)
* [https://github.com/bbatsov/ruby-style-guide#self-assignment](https://github.com/bbatsov/ruby-style-guide#self-assignment)
