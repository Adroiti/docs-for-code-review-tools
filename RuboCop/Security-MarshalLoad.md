Pattern: Security/MarshalLoad

Issue: -

## Description

This cop checks for the use of Marshal class methods which have
potential security issues leading to remote code execution when
loading from an untrusted source.

### Example

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

* [RuboCop - Security/MarshalLoad](https://rubocop.readthedocs.io/en/latest/cops_security/#securitymarshalload)
* [http://ruby-doc.org/core-2.3.3/Marshal.html#module-Marshal-label-Security+considerations](http://ruby-doc.org/core-2.3.3/Marshal.html#module-Marshal-label-Security+considerations)
