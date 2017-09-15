Pattern: Use of `return` in `ensure` block

Issue: -

## Description

If you explicitly return from a method inside an `ensure` block, the return will take precedence over any exception being raised, and the method will return as if no exception had been raised at all. In effect, the exception will be silently thrown away.

### Example

```ruby
# bad

begin
  do_something
ensure
  do_something_else
  return
end
```
```ruby
# good

begin
  do_something
ensure
  do_something_else
end
```

## Further Reading

* [RuboCop - Lint/EnsureReturn](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintensurereturn)
* [https://github.com/bbatsov/ruby-style-guide#no-return-ensure](https://github.com/bbatsov/ruby-style-guide#no-return-ensure)
