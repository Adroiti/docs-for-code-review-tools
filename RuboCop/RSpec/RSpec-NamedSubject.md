Pattern: Missing name for test subject

Issue: -

## Description

Checks for explicitly referenced test subjects.

RSpec lets you declare an "implicit subject" using `subject { ... }`
which allows for tests like `it { should be_valid }`. If you need to
reference your test subject you should explicitly name it using
`subject(:your_subject_name) { ... }`. Your test subjects should be
the most important object in your tests so they deserve a descriptive
name.

This rule can be configured in your configuration using the
`IgnoreSharedExamples` which will not report offenses for implicit
subjects in shared example groups.

## Examples

```ruby
# bad
RSpec.describe User do
  subject { described_class.new }

  it 'is valid' do
    expect(subject.valid?).to be(true)
  end
end

# good
RSpec.describe Foo do
  subject(:user) { described_class.new }

  it 'is valid' do
    expect(user.valid?).to be(true)
  end
end

# also good
RSpec.describe Foo do
  subject(:user) { described_class.new }

  it { should be_valid }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
IgnoreSharedExamples | `true` | Boolean

## Further Reading

* [RSpec - RSpec/NamedSubject](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecnamedsubject)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NamedSubject](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NamedSubject)
