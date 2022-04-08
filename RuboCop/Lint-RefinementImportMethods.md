Pattern: Use of `include`/`prepend` in `refine` block

Issue: -

## Description

This rule checks if `include` or `prepend` is called in `refine` block.
These methods are deprecated and should be replaced with `Refinement#import_methods`.

It emulates deprecation warnings in Ruby 3.1.

## Examples

```ruby
# bad
refine Foo do
  include Bar
end

# bad
refine Foo do
  prepend Bar
end

# good
refine Foo do
  import_methods Bar
end
```

## Further Reading

* [RuboCop - Lint/RefinementImportMethods](https://docs.rubocop.org/rubocop/cops_lint.html#lintrefinementimportmethods)
