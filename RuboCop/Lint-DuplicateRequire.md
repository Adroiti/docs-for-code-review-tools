Pattern: Duplicate `require`/`require_relative`

Issue: -

## Description

This rule checks for duplicate `require`s and `require_relative`s.

## Examples

```ruby
# bad
require 'foo'
require 'bar'
require 'foo'

# good
require 'foo'
require 'bar'

# good
require 'foo'
require_relative 'foo'
```

## Further Reading

* [RuboCop - Lint/DuplicateRequire](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicaterequire)
