Pattern: Deprecated constant

Issue: -

## Description

This rule checks for deprecated constants.

It has `DeprecatedConstants` config. If there is an alternative method, you can set
alternative value as `Alternative`. And you can set the deprecated version as
`DeprecatedVersion`. These options can be omitted if they are not needed.

  DeprecatedConstants:
    'DEPRECATED_CONSTANT':
      Alternative: 'alternative_value'
      DeprecatedVersion: 'deprecated_version'

By default, `NIL`, `TRUE`, `FALSE` and `Random::DEFAULT` are configured.

## Examples

```ruby
# bad
NIL
TRUE
FALSE
Random::DEFAULT # Return value of Ruby 2 is `Random` instance, Ruby 3.0 is `Random` class.

# good
nil
true
false
Random.new # `::DEFAULT` has been deprecated in Ruby 3, `.new` is compatible with Ruby 2.
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
DeprecatedConstants | `{"NIL"=>{"Alternative"=>"nil", "DeprecatedVersion"=>"2.4"}, "TRUE"=>{"Alternative"=>"true", "DeprecatedVersion"=>"2.4"}, "FALSE"=>{"Alternative"=>"false", "DeprecatedVersion"=>"2.4"}, "Random::DEFAULT"=>{"Alternative"=>"Random.new", "DeprecatedVersion"=>"3.0"}}` |

## Further Reading

* [RuboCop - Lint/DeprecatedConstants](https://docs.rubocop.org/rubocop/cops_lint.html#lintdeprecatedconstants)
