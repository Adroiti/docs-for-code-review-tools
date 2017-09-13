Pattern: Style/MultilineIfThen

Issue: -

## Description

Checks for uses of the `then` keyword in multi-line if statements.

### Example

```ruby
if cond then
end
```
```ruby
if cond then a
elsif cond then b
end
```

## Further Reading

* [RuboCop - Style/MultilineIfThen](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultilineifthen)
* [https://github.com/bbatsov/ruby-style-guide#no-then](https://github.com/bbatsov/ruby-style-guide#no-then)
