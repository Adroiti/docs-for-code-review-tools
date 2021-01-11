Pattern: Unexpected block arity

Issue: -

## Description

This rule checks for a block that is known to need more positional
block arguments than are given (by default this is configured for
`Enumerable` methods needing 2 arguments). Optional arguments are allowed,
although they don't generally make sense as the default value will
be used. Blocks that have no receiver, or take splatted arguments
(ie. `*args`) are always accepted.

Keyword arguments (including `**kwargs`) do not get counted towards
this, as they are not used by the methods in question.

NOTE: This rule matches for method names only and hence cannot tell apart
methods with same name in different classes.

Method names and their expected arity can be configured like this:

Methods:
  inject: 2
  reduce: 2

## Examples

```ruby
# bad
values.reduce {}
values.min { |a| a }
values.sort { |a; b| a + b }

# good
values.reduce { |memo, obj| memo << obj }
values.min { |a, b| a <=> b }
values.sort { |*x| x[0] <=> x[1] }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Methods | `{"chunk_while"=>2, "each_with_index"=>2, "each_with_object"=>2, "inject"=>2, "max"=>2, "min"=>2, "minmax"=>2, "reduce"=>2, "slice_when"=>2, "sort"=>2}` |

## Further Reading

* [RuboCop - Lint/UnexpectedBlockArity](https://docs.rubocop.org/rubocop/cops_lint.html#lintunexpectedblockarity)
