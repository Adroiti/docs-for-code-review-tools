Pattern: Unnecessary `require`

Issue: -

## Description

Checks for unnecessary `require` statement.

## Examples

```ruby
# bad
require 'unloaded_feature'
require 'thread'

# good
require 'unloaded_feature'
```

## Further Reading

* [RuboCop - Lint/UnneededRequireStatement](https://docs.rubocop.org/rubocop/cops_lint.html#lintunneededrequirestatement)
