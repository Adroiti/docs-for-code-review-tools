Pattern: Layout/EmptyLinesAroundBlockBody

Issue: -

## Description

This cops checks if empty lines around the bodies of blocks match
the configuration.

### Example

```ruby
# EnforcedStyle: empty_lines

# good

foo do |bar|

  ...

end

# EnforcedStyle: no_empty_lines

# good

foo do |bar|
  ...
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | no_empty_lines
SupportedStyles | empty_lines, no_empty_lines

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundBlockBody](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylinesaroundblockbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
