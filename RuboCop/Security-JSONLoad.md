Pattern: Use of `JSON.load`/`JSON.restore`

Issue: -

## Description

This rule checks for the use of JSON class methods which have potential
security issues.

## Examples

```ruby
# always offense
JSON.load("{}")
JSON.restore("{}")

# no offense
JSON.parse("{}")
```

## Further Reading

* [RuboCop - Security/JSONLoad](https://docs.rubocop.org/rubocop/cops_security.html#securityjsonload)
* [http://ruby-doc.org/stdlib-2.3.0/libdoc/json/rdoc/JSON.html#method-i-load](http://ruby-doc.org/stdlib-2.3.0/libdoc/json/rdoc/JSON.html#method-i-load)
