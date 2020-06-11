Pattern: Redundant escape inside Regexp

Issue: -

## Description

This rule checks for redundant escapes inside Regexp literals.

## Examples

```ruby
# bad
%r{foo\/bar}

# good
%r{foo/bar}

# good
/foo\/bar/

# good
%r/foo\/bar/

# bad
/a\-b/

# good
/a-b/

# bad
/[\+\-]\d/

# good
/[+\-]\d/
```

## Further Reading

* [RuboCop - Style/RedundantRegexpEscape](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantregexpescape)
