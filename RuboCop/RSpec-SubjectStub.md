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

* [RSpec - RSpec/SubjectStub](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecsubjectstub)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SubjectStub](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SubjectStub)
