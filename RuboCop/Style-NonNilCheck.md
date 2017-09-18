Pattern: Redundant nil check

Issue: -

## Description

This rule checks for non-nil checks, which are usually redundant. Non-nil checks are allowed if they are the final nodes of predicate.

## Examples

```ruby
# bad
if x != nil

# good (when not allowing semantic changes)
# bad (when allowing semantic changes)
if !x.nil?

# good (when allowing semantic changes)
if x
```

## Default configuration

Attribute | Value
--- | ---
IncludeSemanticChanges | false

## Further Reading

* [RuboCop - Style/NonNilCheck](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenonnilcheck)
* [https://github.com/bbatsov/ruby-style-guide#no-non-nil-checks](https://github.com/bbatsov/ruby-style-guide#no-non-nil-checks)
