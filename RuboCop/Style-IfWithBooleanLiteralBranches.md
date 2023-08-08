Pattern: `if` with boolean literal branches

Issue: -

## Description

This rule checks for redundant `if` with boolean literal branches. It checks only conditions to return boolean value (`true` or `false`) for safe detection. The conditions to be checked are comparison methods, predicate methods, and double negative. However, auto-correction is unsafe because there is no guarantee that all predicate methods will return boolean value. Those methods can be allowed with `AllowedMethods` config.

## Examples

```ruby
# bad
if foo == bar
  true
else
  false
end

# bad
foo == bar ? true : false

# good
foo == bar
```


## Further Reading

* [RuboCop - Style/IfWithBooleanLiteralBranches](https://docs.rubocop.org/rubocop/cops_style.html#styleifwithbooleanliteralbranches)
