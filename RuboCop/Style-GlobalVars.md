Pattern: Style/GlobalVars

Issue: -

## Description

This cops looks for uses of global variables.
It does not report offenses for built-in global variables.
Built-in global variables are allowed by default. Additionally
users can allow additional variables via the AllowedVariables option.

Note that backreferences like $1, $2, etc are not global variables.

## Default configuration

Attribute | Value
--- | ---
AllowedVariables |

## Further Reading

* [RuboCop - Style/GlobalVars](https://rubocop.readthedocs.io/en/latest/cops_style/#styleglobalvars)
* [https://github.com/bbatsov/ruby-style-guide#instance-vars](https://github.com/bbatsov/ruby-style-guide#instance-vars)
* [http://www.zenspider.com/Languages/Ruby/QuickRef.html](http://www.zenspider.com/Languages/Ruby/QuickRef.html)
