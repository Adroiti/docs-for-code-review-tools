Pattern: `expect()` without `.to` or `.not_to`

Issue: -

## Description

This rule checks void `expect()`.

## Examples

```ruby
# bad
expect(something)

# good
expect(something).to be(1)
```

## Further Reading

* [RSpec - RSpec/VoidExpect](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecvoidexpect)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VoidExpect](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VoidExpect)
