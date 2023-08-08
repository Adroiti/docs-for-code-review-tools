Pattern: Redundant self assignment

Issue: -

## Description

This rule checks for places where redundant assignments are made for in place
modification methods.

This rule is marked as unsafe, because it can produce false positives for
user defined methods having one of the expected names, but not modifying
its receiver in place.

## Examples

```ruby
# bad
args = args.concat(ary)
hash = hash.merge!(other)

# good
args.concat(foo)
args += foo
hash.merge!(other)

# bad
self.foo = foo.concat(ary)

# good
foo.concat(ary)
self.foo += ary
```

## Further Reading

* [RuboCop - Style/RedundantSelfAssignment](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantselfassignment)
