Pattern: Inconsistent use of `be_a`/`be_kind_of`

Issue: -

## Description

Enforces consistent use of `be_a` or `be_kind_of`.

## Examples

#### EnforcedStyle: be_a (default)

```ruby
# bad
expect(object).to be_kind_of(String)
expect(object).to be_a_kind_of(String)

# good
expect(object).to be_a(String)
expect(object).to be_an(String)
```

#### EnforcedStyle: be_kind_of

```ruby
# bad
expect(object).to be_a(String)
expect(object).to be_an(String)

# good
expect(object).to be_kind_of(String)
expect(object).to be_a_kind_of(String)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `be_a` | `be_a`, `be_kind_of`

## Further Reading

* [RSpec - RSpec/ClassCheck](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecclasscheck)
* https://rubystyle.guide#is-a-vs-kind-of
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ClassCheck