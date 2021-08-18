Pattern: Use of `bundler/setup` in test

Issue: -

## Description

Flags the `require "bundler/setup"` calls if they're made from inside the tests directory.

## Examples

```ruby
# bad
require "foo"
require "bundler/setup"

# good
require "foo"
```

## Further Reading

* [RuboCop - Performance/BundlerSetupInTests](https://github.com/utkarsh2102/rubocop-packaging/blob/master/lib/rubocop/cop/packaging/bundler_setup_in_tests.rb)