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

* [RuboCop - Lint/RedundantRequireStatement](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintredundantrequirestatement)
