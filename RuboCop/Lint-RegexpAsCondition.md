Pattern: Regexp as condition

Issue: -

## Description

This rule checks for regexp literals used as `match-current-line`.
If a regexp literal is in condition, the regexp matches `$_` implicitly.

### Example

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

* [RuboCop - Lint/RegexpAsCondition](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintregexpascondition)
