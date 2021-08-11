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

* [RSpec - RSpec/VoidExpect](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecvoidexpect)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VoidExpect](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VoidExpect)
