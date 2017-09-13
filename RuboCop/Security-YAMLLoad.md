Pattern: Security/YAMLLoad

Issue: -

## Description

This cop checks for the use of YAML class methods which have
potential security issues leading to remote code execution when
loading from an untrusted source.

### Example

```ruby
# bad
YAML.load("--- foo")

# good
YAML.safe_load("--- foo")
YAML.dump("foo")
```

## Further Reading

* [RuboCop - Security/YAMLLoad](https://rubocop.readthedocs.io/en/latest/cops_security/#securityyamlload)
* [https://ruby-doc.org/stdlib-2.3.3/libdoc/yaml/rdoc/YAML.html#module-YAML-label-Security](https://ruby-doc.org/stdlib-2.3.3/libdoc/yaml/rdoc/YAML.html#module-YAML-label-Security)
