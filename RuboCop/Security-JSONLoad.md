Pattern: Use of `JSON.load`/`JSON.restore`

Issue: -

## Description

This cop checks for the use of JSON class methods which have potential
security issues.

### Example

```ruby
# always offense
JSON.load("{}")
JSON.restore("{}")

# no offense
JSON.parse("{}")
```

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false

## Further Reading

* [RuboCop - Security/JSONLoad](https://rubocop.readthedocs.io/en/latest/cops_security/#securityjsonload)
* [http://ruby-doc.org/stdlib-2.3.0/libdoc/json/rdoc/JSON.html#method-i-load](http://ruby-doc.org/stdlib-2.3.0/libdoc/json/rdoc/JSON.html#method-i-load)
