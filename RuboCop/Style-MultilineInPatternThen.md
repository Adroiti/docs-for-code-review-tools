Pattern: Use of `then` for multi-line `in` statement

Issue: -

## Description

Checks uses of the `then` keyword in multi-line `in` statement.
 
## Examples

```ruby
# bad
case expression
in pattern then
end

# good
case expression
in pattern
end

# good
case expression
in pattern then do_something
end

# good
case expression
in pattern then do_something(arg1,
                             arg2)
end
```

## Further Reading

* [RuboCop - Style/MultilineInPatternThen](https://docs.rubocop.org/rubocop/cops_style.html#stylemultilineinpatternthen)