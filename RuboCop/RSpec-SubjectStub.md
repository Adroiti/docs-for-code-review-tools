Pattern: Stubbed test subject

Issue: -

## Description

Checks for stubbed test subjects.

## Examples

```ruby
# bad
describe Foo do
  subject(:bar) { baz }

  before do
    allow(bar).to receive(:qux?).and_return(true)
  end
end
```

## Further Reading

* [RSpec - RSpec/SubjectStub](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecsubjectstub)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SubjectStub](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SubjectStub)
