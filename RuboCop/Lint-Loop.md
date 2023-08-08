Pattern: Missing use of `Kernel#loop` with `break`

Issue: -

## Description

This rule checks for uses of `begin...end while/until something`.

## Examples

```ruby
# bad

# using while
begin
  do_something
end while some_condition
```
```ruby
# bad

# using until
begin
  do_something
end until some_condition
```
```ruby
# good

# using while
while some_condition
  do_something
end
```
```ruby
# good

# using until
until some_condition
  do_something
end
```

## Further Reading

* [RuboCop - Lint/Loop](https://docs.rubocop.org/rubocop/cops_lint.html#lintloop)
* [https://github.com/bbatsov/ruby-style-guide#loop-with-break](https://github.com/bbatsov/ruby-style-guide#loop-with-break)
