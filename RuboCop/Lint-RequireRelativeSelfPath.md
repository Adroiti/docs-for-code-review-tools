Pattern: Use of `require_relative` that requires itself

Issue: -

## Description

Checks for uses a file requiring itself with `require_relative`.

## Examples

```ruby
# bad

# foo.rb
require_relative 'foo'
require_relative 'bar'

# good

# foo.rb
require_relative 'bar'
```

## Further Reading

* [RuboCop - Lint/RequireRelativeSelfPath](https://docs.rubocop.org/rubocop/cops_lint.html#lintrequirerelativeselfpath)
