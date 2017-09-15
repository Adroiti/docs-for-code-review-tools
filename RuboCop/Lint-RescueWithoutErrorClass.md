Pattern: `rescue` without error class

Issue: -

## Description

This cop checks for uses of `rescue` with no error class specified.

### Example

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
