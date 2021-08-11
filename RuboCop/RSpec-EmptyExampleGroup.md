Pattern: Empty example group

Issue: -

## Description

Checks if an example group does not include any tests.

This rule is configurable using the `CustomIncludeMethods` option

## Examples

#### usage

```ruby
# bad
describe Bacon do
  let(:bacon)      { Bacon.new(chunkiness) }
  let(:chunkiness) { false                 }

  context 'extra chunky' do   # flagged by rubocop
    let(:chunkiness) { true }
  end

  it 'is chunky' do
    expect(bacon.chunky?).to be_truthy
  end
end

# good
describe Bacon do
  let(:bacon)      { Bacon.new(chunkiness) }
  let(:chunkiness) { false                 }

  it 'is chunky' do
    expect(bacon.chunky?).to be_truthy
  end
end
```
#### configuration

```ruby
# .rubocop.yml
# RSpec/EmptyExampleGroup:
#   CustomIncludeMethods:
#   - include_tests

# spec_helper.rb
RSpec.configure do |config|
  config.alias_it_behaves_like_to(:include_tests)
end

# bacon_spec.rb
describe Bacon do
  let(:bacon)      { Bacon.new(chunkiness) }
  let(:chunkiness) { false                 }

  context 'extra chunky' do   # not flagged by rubocop
    let(:chunkiness) { true }

    include_tests 'shared tests'
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CustomIncludeMethods | `[]` | Array

## Further Reading

* [RSpec - RSpec/EmptyExampleGroup](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptyexamplegroup)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyExampleGroup](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyExampleGroup)
