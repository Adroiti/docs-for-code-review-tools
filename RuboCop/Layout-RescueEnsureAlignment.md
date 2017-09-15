Pattern: Misaligned `rescue`/`ensure`

Issue: -

## Description

This cop checks whether the `rescue` and `ensure` keywords are aligned properly.

### Example

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

* [RuboCop - Layout/RescueEnsureAlignment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutrescueensurealignment)
