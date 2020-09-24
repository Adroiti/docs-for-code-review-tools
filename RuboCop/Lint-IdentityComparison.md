Pattern: Use of `==` when comparing `object_id`

Issue: -

## Description

Prefer `equal?` over `==` when comparing `object_id`.

`Object#equal?` is provided to compare objects for identity, and in contrast
`Object#==` is provided for the purpose of doing value comparison.

## Examples

```ruby
# bad
foo.object_id == bar.object_id

# good
foo.equal?(bar)
```

## Further Reading

* [RuboCop - Lint/IdentityComparison](https://docs.rubocop.org/rubocop/cops_lint.html#lintidentitycomparison)
* [The Ruby Style Guide](https://rubystyle.guide#identity-comparison)