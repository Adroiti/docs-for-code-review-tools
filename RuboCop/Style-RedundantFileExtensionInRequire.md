Pattern: Redundant file extension in `require`

Issue: -

## Description

Checks for the presence of superfluous `.rb` extension in the filename provided to `require` and `require_relative`.

Note: If the extension is omitted, Ruby tries adding '.rb', '.so', and so on to the name until found. If the file named cannot be found, a `LoadError` will be raised. There is an edge case where foo.so file is loaded instead of a `LoadError` if `foo.so` file exists when `require 'foo.rb'` will be changed to require 'foo', but that seems harmless.


## Examples

```ruby
# bad
require 'foo.rb'
require_relative '../foo.rb'

# good
require 'foo'
require 'foo.so'
require_relative '../foo'
require_relative '../foo.so'

```

## Further Reading

* [RuboCop - Style/RedundantFileExtensionInRequire](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantfileextensioninrequire)
