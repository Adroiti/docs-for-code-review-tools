Pattern: Style/IfUnlessModifierOfIfUnless

Issue: -

## Description

Checks for if and unless statements used as modifiers of other if or
unless statements.

### Example

```ruby
# bad
tired? ? 'stop' : 'go faster' if running?

# bad
if tired?
  "please stop"
else
  "keep going"
end if running?

# good
if running?
  tired? ? 'stop' : 'go faster'
end
```

## Further Reading

* [RuboCop - Style/IfUnlessModifierOfIfUnless](https://rubocop.readthedocs.io/en/latest/cops_style/#styleifunlessmodifierofifunless)
