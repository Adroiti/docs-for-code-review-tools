Pattern: Missing use of `require`

Issue: -

## Description

Checks for missing require statements in your code.

## Examples 

```ryby
# bad
Faraday.new

# good
require 'faraday'

Faraday.new
```

## Further Reading

* [RuboCop - MissingRequireStatement](https://github.com/milch/rubocop-require_tools/blob/master/lib/rubocop/cop/require/missing_require_statement.rb)
