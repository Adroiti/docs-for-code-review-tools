Pattern: Use of `rescue` without error class

Issue: -

## Description

This rule checks for uses of `rescue` with no error class specified.

## Examples

```ruby
# good
begin
  foo
rescue BarError
  bar
end

# bad
begin
  foo
rescue
  bar
end
```

## Further Reading

* [RuboCop - Lint/RescueWithoutErrorClass](https://docs.rubocop.org/rubocop/cops_lint.html#lintrescuewithouterrorclass)
* [https://github.com/bbatsov/ruby-style-guide#no-blind-rescues](https://github.com/bbatsov/ruby-style-guide#no-blind-rescues)
