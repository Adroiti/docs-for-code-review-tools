Pattern: Malformed use of `subject`

Issue: -

## Description

Enforce that `subject` is the first definition in the test.

## Examples

```ruby
# bad
  let(:params) { blah }
  subject { described_class.new(params) }

  before { do_something }
  subject { described_class.new(params) }

  it { expect_something }
  subject { described_class.new(params) }
  it { expect_something_else }

# good
  subject { described_class.new(params) }
  let(:params) { blah }

# good
  subject { described_class.new(params) }
  before { do_something }

# good
  subject { described_class.new(params) }
  it { expect_something }
  it { expect_something_else }
```

## Further Reading

* [RSpec - RSpec/LeadingSubject](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecleadingsubject)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LeadingSubject](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/LeadingSubject)
