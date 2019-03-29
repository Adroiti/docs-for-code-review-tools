Pattern: Inconsistent use of `it_behaves_like`/`it_should_behave_like`

Issue: -

## Description

Checks that only one `it_behaves_like` style is used.

## Examples

#### when configuration is `EnforcedStyle: it_behaves_like`

```ruby
# bad
it_should_behave_like 'a foo'

# good
it_behaves_like 'a foo'
```
#### when configuration is `EnforcedStyle: it_should_behave_like`

```ruby
# bad
it_behaves_like 'a foo'

# good
it_should_behave_like 'a foo'
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `it_behaves_like` | `it_behaves_like`, `it_should_behave_like`

## Further Reading

* [RSpec - RSpec/ItBehavesLike](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecitbehaveslike)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ItBehavesLike](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ItBehavesLike)
