Pattern: Redundant safe navigation

Issue: -

## Description

Checks for redundant safe navigation calls. `instance_of?`, `kind_of?`, `is_a?`, `eql?`, `respond_to?`, and `equal?` methods are checked by default. These are customizable with `AllowedMethods` option.

This rule is marked as unsafe, because auto-correction can change the return type of the expression. An offending expression that previously could return nil will be auto-corrected to never return nil.

In the example below, the safe navigation operator (`&.`) is unnecessary because `NilClass` has methods like `respond_to?` and `is_a?`.

## Examples

```ruby
# bad
do_something if attrs&.respond_to?(:[])

# good
do_something if attrs.respond_to?(:[])

# bad
while node&.is_a?(BeginNode)
  node = node.parent
end

# good
while node.is_a?(BeginNode)
  node = node.parent
end

# good - without `&.` this will always return `true`
foo&.respond_to?(:to_a)
```

## Further Reading

* [RuboCop - Lint/RedundantSafeNavigation](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantsafenavigation)
