Pattern: Missing use of `||=`

Issue: -

## Description

This rule checks for potential usage of the `||=` operator.

## Examples

```ruby
# bad
name = name ? name : 'Bozhidar'

# bad
name = 'Bozhidar' unless name

# good - set name to 'Bozhidar', only if it's nil or false
name ||= 'Bozhidar'
```

## Further Reading

* [RuboCop - Style/OrAssignment](https://docs.rubocop.org/rubocop/cops_style.html#styleorassignment)
* [https://github.com/bbatsov/ruby-style-guide#double-pipe-for-uninit](https://github.com/bbatsov/ruby-style-guide#double-pipe-for-uninit)
