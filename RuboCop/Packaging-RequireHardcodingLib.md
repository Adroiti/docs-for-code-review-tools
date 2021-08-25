Pattern: Use of hardcoded `lib`

Issue: -

## Description

Flags the `require` calls, from anywhere mapping to the "lib" directory, except originating from lib/.

## Examples

```ruby
# bad
require "../lib/foo/bar"

# good
require "foo/bar"

# bad
require File.expand_path("../../lib/foo", __FILE__)

# good
require "foo"

# bad
require File.expand_path("../../../lib/foo/bar/baz/qux", __dir__)

# good
require "foo/bar/baz/qux"

# bad
require File.dirname(__FILE__) + "/../../lib/baz/qux"

# good
require "baz/qux"

```

## Further Reading

* [RuboCop - Performance/RequireHardcodingLib](https://github.com/utkarsh2102/rubocop-packaging/blob/master/lib/rubocop/cop/packaging/require_hardcoding_lib.rb)