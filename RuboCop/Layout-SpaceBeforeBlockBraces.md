Pattern: Malformed space before block brace

Issue: -

## Description

Checks that block braces have or don't have a space before the opening brace depending on configuration.

## Examples

```ruby
# bad
foo.map{ |a|
  a.bar.to_s
}

# good
foo.map { |a|
  a.bar.to_s
}
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | space
SupportedStyles | space, no_space
SupportedStylesForEmptyBraces | space, no_space

## Further Reading

* [RuboCop - Layout/SpaceBeforeBlockBraces](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacebeforeblockbraces)
