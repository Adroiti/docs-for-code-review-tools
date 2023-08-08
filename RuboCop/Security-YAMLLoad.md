Pattern: Use of `YAML.load`

Issue: -

## Description

This rule checks for the use of YAML class methods which have
potential security issues leading to remote code execution when
loading from an untrusted source.

## Examples

```ruby
# bad
YAML.load("--- foo")

# good
YAML.safe_load("--- foo")
YAML.dump("foo")
```

## Further Reading

* [Documentation for Ruby - YAML](https://docs.ruby-lang.org/en/2.0.0/security_rdoc.html#label-YAML)
* [RuboCop - Security/YAMLLoad](https://docs.rubocop.org/rubocop/cops_security.html#securityyamlload)
