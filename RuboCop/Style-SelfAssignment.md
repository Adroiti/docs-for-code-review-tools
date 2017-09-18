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

* [RuboCop - Style/SelfAssignment](https://rubocop.readthedocs.io/en/latest/cops_style/#styleselfassignment)
* [https://github.com/bbatsov/ruby-style-guide#self-assignment](https://github.com/bbatsov/ruby-style-guide#self-assignment)
