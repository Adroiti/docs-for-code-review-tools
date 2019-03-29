Pattern: Use of `let` after example

Issue: -

## Description

Checks for `let` definitions that come after an example.

## Examples

```ruby
# Bad
let(:foo) { bar }

it 'checks what foo does' do
  expect(foo).to be
end

let(:some) { other }

it 'checks what some does' do
  expect(some).to be
end

# Good
let(:foo) { bar }
let(:some) { other }

it 'checks what foo does' do
  expect(foo).to be
end

it 'checks what some does' do
  expect(some).to be
end
```

## Further Reading

* [RSpec - RSpec/LetBeforeExamples](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecletbeforeexamples)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LetBeforeExamples](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LetBeforeExamples)
