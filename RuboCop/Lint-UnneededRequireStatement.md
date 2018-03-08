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

* [RuboCop - Lint/UnneededRequireStatement](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunneededrequirestatement)
