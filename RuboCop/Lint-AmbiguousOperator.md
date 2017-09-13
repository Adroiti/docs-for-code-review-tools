Pattern: Lint/AmbiguousOperator

Issue: -

## Description

This cop checks for ambiguous operators in the first argument of a
method invocation without parentheses.

### Example

```ruby
# bad

# The `*` is interpreted as a splat operator but it could possibly be
# a `*` method invocation (i.e. `do_something.*(some_array)`).
do_something *some_array
```
```ruby
# good

# With parentheses, there's no ambiguity.
do_something(*some_array)
```

## Further Reading

* [RuboCop - Lint/AmbiguousOperator](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintambiguousoperator)
* [https://github.com/bbatsov/ruby-style-guide#method-invocation-parens](https://github.com/bbatsov/ruby-style-guide#method-invocation-parens)
