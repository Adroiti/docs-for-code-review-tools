Pattern: Use of `then` in multi-line `when`

Issue: -

## Description

Checks uses of the `then` keyword in multi-line `when` statements.

## Examples

```ruby
# bad
case foo
when bar then
end

# good
case foo
when bar
end

# good
case foo
when bar then do_something
end
```

## Further Reading

* [RuboCop - Style/MultilineWhenThen](https://docs.rubocop.org/rubocop/cops_style.html#stylemultilinewhenthen)
