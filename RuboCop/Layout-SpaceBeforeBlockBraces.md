Pattern: Layout/SpaceBeforeBlockBraces

Issue: -

## Description

Checks that block braces have or don't have a space before the opening
brace depending on configuration.

### Example

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

* [RuboCop - Layout/SpaceBeforeBlockBraces](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspacebeforeblockbraces)
