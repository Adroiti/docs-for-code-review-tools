Pattern: Use of `$stderr.puts()`

Issue: -

## Description

This rule identifies places where `$stderr.puts` can be replaced by
`warn`. The latter has the advantage of easily being disabled by,
e.g. the `-W0` interpreter flag, or setting `$VERBOSE` to nil.

## Examples

```ruby
# bad
$stderr.puts('hello')

# good
warn('hello')
```

## Further Reading

* [RuboCop - Style/StderrPuts](https://docs.rubocop.org/rubocop/cops_style.html#stylestderrputs)
* [https://github.com/bbatsov/ruby-style-guide#warn](https://github.com/bbatsov/ruby-style-guide#warn)
