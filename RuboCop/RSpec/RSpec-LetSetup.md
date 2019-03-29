Pattern: Unreferenced `let!` call

Issue: -

## Description

Checks unreferenced `let!` calls being used for test setup.

## Examples

```ruby
# Bad
let!(:my_widget) { create(:widget) }

it 'counts widgets' do
  expect(Widget.count).to eq(1)
end

# Good
it 'counts widgets' do
  create(:widget)
  expect(Widget.count).to eq(1)
end

# Good
before { create(:widget) }

it 'counts widgets' do
  expect(Widget.count).to eq(1)
end
```

## Further Reading

* [RSpec - RSpec/LetSetup](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecletsetup)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LetSetup](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LetSetup)
