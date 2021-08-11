Pattern: Use of hook after example

Issue: -

## Description

Checks for `before`/`around`/`after` hooks that come after an example.

## Examples

```ruby
# Bad

it 'checks what foo does' do
  expect(foo).to be
end

before { prepare }
after { clean_up }

# Good
before { prepare }
after { clean_up }

it 'checks what foo does' do
  expect(foo).to be
end
```

## Further Reading

* [RSpec - RSpec/HooksBeforeExamples](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspechooksbeforeexamples)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/HooksBeforeExamples](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/HooksBeforeExamples)
