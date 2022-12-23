Pattern: Redundant double splat hash braces

Issue: -

## Description

Checks for redundant uses of double splat hash braces.

## Examples

```ruby
# bad
do_something(**{foo: bar, baz: qux})

# good
do_something(foo: bar, baz: qux)
```

## Further Reading

* [RuboCop - Style/RedundantDoubleSplatHashBraces](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantdoublesplathashbraces)
