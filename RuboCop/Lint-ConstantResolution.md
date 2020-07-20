Pattern: Use of not fully qualified constant

Issue: -

## Description

Checks that certain constants are fully qualified.

Generally, gems should fully qualify all constants to avoid conflicts with the code that uses the gem. Enable this cop without using `Only/Ignore`.

## Examples

```ruby
# By default checks every constant

# bad
User

# bad
User::Login

# good
::User

# good
::User::Login
```

## Further Reading

* [RuboCop - Lint/ConstantResolution](https://docs.rubocop.org/rubocop/cops_lint.html#lintconstantresolution)
