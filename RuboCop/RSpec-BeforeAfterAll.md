Pattern: Use of `before`/`after(:all)`

Issue: -

## Description

Checks that `before`/`after(:all)` isn't being used.

## Examples

```ruby
# bad
#
# Faster but risk of state leaking between examples
#
describe MyClass do
  before(:all) { Widget.create }
  after(:all) { Widget.delete_all }
end

# good
#
# Slower but examples are properly isolated
#
describe MyClass do
  before(:each) { Widget.create }
  after(:each) { Widget.delete_all }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Exclude | `spec/spec_helper.rb`, `spec/rails_helper.rb`, `spec/support/**/*.rb` | Array

## Further Reading

* [RSpec - RSpec/BeforeAfterAll](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecbeforeafterall)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/BeforeAfterAll](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/BeforeAfterAll)
