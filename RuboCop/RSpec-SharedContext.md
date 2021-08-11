Pattern: Malformed `shared_context`/`shared_examples`

Issue: -

## Description

Checks for proper `shared_context` and `shared_examples` usage.

If there are no examples defined, use `shared_context`. If there is no setup defined, use `shared_examples`.

## Examples

```ruby
# bad
RSpec.shared_context 'only examples here' do
  it 'does x' do
  end

  it 'does y' do
  end
end

# good
RSpec.shared_examples 'only examples here' do
  it 'does x' do
  end

  it 'does y' do
  end
end
```
```ruby
# bad
RSpec.shared_examples 'only setup here' do
  subject(:foo) { :bar }

  let(:baz) { :bazz }

  before do
    something
  end
end

# good
RSpec.shared_context 'only setup here' do
  subject(:foo) { :bar }

  let(:baz) { :bazz }

  before do
    something
  end
end
```

## Further Reading

* [RSpec - RSpec/SharedContext](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecsharedcontext)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SharedContext](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SharedContext)
