Pattern: Use of `Marshal.`

Issue: -

## Description

This rule checks for the use of Marshal class methods which have
potential security issues leading to remote code execution when
loading from an untrusted source.

## Examples

```ruby
# bad
Marshal.load("{}")
Marshal.restore("{}")

# good
Marshal.dump("{}")

# okish - deep copy hack
Marshal.load(Marshal.dump({}))
```

## Further Reading

* [Documentation for Ruby - Marshal.load](https://docs.ruby-lang.org/en/2.0.0/security_rdoc.html#label-Marshal.load)
* [RuboCop - Security/MarshalLoad](https://rubocop.readthedocs.io/en/latest/cops_security/#securitymarshalload)
