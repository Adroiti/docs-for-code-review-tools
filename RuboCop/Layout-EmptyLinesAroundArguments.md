Pattern: Empty lines around arguments

Issue: -

## Description

This rule checks if empty lines exist around the arguments of a method invocation.

## Examples

```ruby
# bad
do_something(
  foo

)

process(bar,

        baz: qux,
        thud: fred)

some_method(

  [1,2,3],
  x: y
)

# good
do_something(
  foo
)

process(bar,
        baz: qux,
        thud: fred)

some_method(
  [1,2,3],
  x: y
)
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundArguments](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundarguments)
