Pattern: Malformed spacing around block body

Issue: -

## Description

This rule checks if empty lines around the bodies of blocks match the configuration.

## Examples

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

* [RuboCop - Layout/EmptyLinesAroundBlockBody](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundblockbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
