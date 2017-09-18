Pattern: Use of custom global variable

Issue: -

## Description

This rule looks for uses of global variables.
It does not report offenses for built-in global variables.
Built-in global variables are allowed by default. Additionally
users can allow additional variables via the AllowedVariables option.

Note that backreferences like `$1`, `$2`, etc are not global variables.

## Examples

```ruby
# bad
$foo_bar = 1

# good
module Foo
  class << self
    attr_accessor :bar
  end
end

Foo.bar = 1
```

## Default configuration

Attribute | Value
--- | ---
AllowedVariables |

## Further Reading

* [RuboCop - Style/GlobalVars](https://rubocop.readthedocs.io/en/latest/cops_style/#styleglobalvars)
* [https://github.com/bbatsov/ruby-style-guide#instance-vars](https://github.com/bbatsov/ruby-style-guide#instance-vars)
* [http://www.zenspider.com/Languages/Ruby/QuickRef.html](http://www.zenspider.com/Languages/Ruby/QuickRef.html)
