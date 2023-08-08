Pattern: Redundant `require`

Issue: -

## Description

Checks for redundant `require` statement.

## Examples

```ruby
# bad
require 'unloaded_feature'
require 'thread'

# good
require 'unloaded_feature'
```

## Further Reading

* [RuboCop - Lint/RedundantRequireStatement](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantrequirestatement)
