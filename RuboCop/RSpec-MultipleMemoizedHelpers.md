Pattern: Too many memoized helpers

Issue: -

## Description

Checks if example groups contain too many `let` and `subject` calls.

This rule is configurable using the `Max` option and the `AllowSubject`
which will configure the rule to only register offenses on calls to
`let` and not calls to `subject`.

## Examples

```ruby
# bad
describe MyClass do
  let(:foo) { [] }
  let(:bar) { [] }
  let!(:baz) { [] }
  let(:qux) { [] }
  let(:quux) { [] }
  let(:quuz) { {} }
end

describe MyClass do
  let(:foo) { [] }
  let(:bar) { [] }
  let!(:baz) { [] }

  context 'when stuff' do
    let(:qux) { [] }
    let(:quux) { [] }
    let(:quuz) { {} }
  end
end

# good
describe MyClass do
  let(:bar) { [] }
  let!(:baz) { [] }
  let(:qux) { [] }
  let(:quux) { [] }
  let(:quuz) { {} }
end

describe MyClass do
  context 'when stuff' do
    let(:foo) { [] }
    let(:bar) { [] }
    let!(:booger) { [] }
  end

  context 'when other stuff' do
    let(:qux) { [] }
    let(:quux) { [] }
    let(:quuz) { {} }
  end
end
```

#### when disabling AllowSubject configuration

```ruby
# rubocop.yml
# RSpec/MultipleMemoizedHelpers:
#   AllowSubject: false

# bad - `subject` counts towards memoized helpers
describe MyClass do
  subject { {} }
  let(:foo) { [] }
  let(:bar) { [] }
  let!(:baz) { [] }
  let(:qux) { [] }
  let(:quux) { [] }
end
```

#### with Max configuration

```ruby
# rubocop.yml
# RSpec/MultipleMemoizedHelpers:
#   Max: 1

# bad
describe MyClass do
  let(:foo) { [] }
  let(:bar) { [] }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowSubject | `true` | Boolean
Max | `5` | Integer

## Further Reading

* [RSpec - RSpec/MultipleMemoizedHelpers](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmultiplememoizedhelpers)