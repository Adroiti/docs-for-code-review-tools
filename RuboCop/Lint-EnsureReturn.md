Pattern: Lint/EnsureReturn

Issue: -

## Description

This cop checks for *return* from an *ensure* block.

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
