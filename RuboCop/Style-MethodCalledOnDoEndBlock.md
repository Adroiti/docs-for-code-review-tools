Pattern: Method called on do end block

Issue: -

## Description

This cop checks for methods called on a do...end block. The point of
this check is that it's easy to miss the call tacked on to the block
when reading code.

### Example

```ruby
a do
  b
end.c
```

## Further Reading

* [RuboCop - Style/MethodCalledOnDoEndBlock](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemethodcalledondoendblock)
* [https://github.com/bbatsov/ruby-style-guide#single-line-blocks](https://github.com/bbatsov/ruby-style-guide#single-line-blocks)
