Pattern: `rescue` without error class

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

* [RuboCop - Lint/RescueWithoutErrorClass](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintrescuewithouterrorclass)
* [https://github.com/bbatsov/ruby-style-guide#no-blind-rescues](https://github.com/bbatsov/ruby-style-guide#no-blind-rescues)
