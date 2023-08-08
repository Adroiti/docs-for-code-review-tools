Pattern: Misaligned `rescue`/`ensure`

Issue: -

## Description

This rule checks whether the `rescue` and `ensure` keywords are aligned properly.

## Examples

```ruby
# bad
begin
  something
  rescue
  puts 'error'
end

# good
begin
  something
rescue
  puts 'error'
end
```

## Further Reading

* [RuboCop - Layout/RescueEnsureAlignment](https://docs.rubocop.org/rubocop/cops_layout.html#layoutrescueensurealignment)
