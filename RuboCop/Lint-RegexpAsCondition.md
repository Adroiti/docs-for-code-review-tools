Pattern: Regexp as condition

Issue: -

## Description

This rule checks for regexp literals used as `match-current-line`.
If a regexp literal is in condition, the regexp matches `$_` implicitly.

## Examples

```ruby
# bad
if /foo/
  do_something
end

# good
if /foo/ =~ $_
  do_something
end
```

## Further Reading

* [RuboCop - Lint/RegexpAsCondition](https://docs.rubocop.org/rubocop/cops_lint.html#lintregexpascondition)
