Pattern: Use of `then` for multi-line `if`

Issue: -

## Description

Checks for uses of the `then` keyword in multi-line `if` statements.

## Examples

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

* [RuboCop - Style/MultilineIfThen](https://docs.rubocop.org/rubocop/cops_style.html#stylemultilineifthen)
* [https://github.com/bbatsov/ruby-style-guide#no-then](https://github.com/bbatsov/ruby-style-guide#no-then)
