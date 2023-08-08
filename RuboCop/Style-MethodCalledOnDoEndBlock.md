Pattern: Method call on `do...end` block

Issue: -

## Description

This rule checks for methods called on a `do...end` block. The point of
this check is that it's easy to miss the call tacked on to the block
when reading code.

## Examples

```ruby
a do
  b
end.c
```

## Further Reading

* [RuboCop - Style/MethodCalledOnDoEndBlock](https://docs.rubocop.org/rubocop/cops_style.html#stylemethodcalledondoendblock)
* [https://github.com/bbatsov/ruby-style-guide#single-line-blocks](https://github.com/bbatsov/ruby-style-guide#single-line-blocks)
