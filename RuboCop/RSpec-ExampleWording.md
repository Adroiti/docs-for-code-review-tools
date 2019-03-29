Pattern: Malformed example description

Issue: -

## Description

Checks for common mistakes in example descriptions.

This rule will correct docstrings that begin with 'should' and 'it'.

The autocorrect is experimental - use with care! It can be configured
with CustomTransform (e.g. have => has) and IgnoredWords (e.g. only).

## Examples

```ruby
# bad
it 'should find nothing' do
end

# good
it 'finds nothing' do
end
```
```ruby
# bad
it 'it does things' do
end

# good
it 'does things' do
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CustomTransform | `{"be"=>"is", "BE"=>"IS", "have"=>"has", "HAVE"=>"HAS"}` | 
IgnoredWords | `[]` | Array

## Further Reading

* [RSpec - RSpec/ExampleWording](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexamplewording)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleWording](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleWording)
