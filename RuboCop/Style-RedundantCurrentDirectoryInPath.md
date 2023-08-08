Pattern: Redundant current directory in path

Issue: -

## Description

Checks for uses a redundant current directory in path.

## Examples

```ruby
# bad
require_relative './path/to/feature'

# good
require_relative 'path/to/feature'
```

## Further Reading

* [RuboCop - Style/RedundantCurrentDirectoryInPath](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantcurrentdirectoryinpath)
