Pattern: Or assignment

Issue: -

## Description

This cop checks for potential usage of the `||=` operator.

### Example

```ruby
# bad
name = name ? name : 'Bozhidar'

# bad
name = if name
         name
       else
         'Bozhidar'
       end

# bad
unless name
  name = 'Bozhidar'
end

# bad
name = 'Bozhidar' unless name

# good - set name to 'Bozhidar', only if it's nil or false
name ||= 'Bozhidar'
```

## Further Reading

* [RuboCop - Style/OrAssignment](https://rubocop.readthedocs.io/en/latest/cops_style/#styleorassignment)
* [https://github.com/bbatsov/ruby-style-guide#double-pipe-for-uninit](https://github.com/bbatsov/ruby-style-guide#double-pipe-for-uninit)
