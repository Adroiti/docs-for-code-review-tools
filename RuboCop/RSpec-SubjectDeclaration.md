Pattern: Ambiguous declaration of subject

Issue: -

## Description

Ensure that subject is defined using subject helper.

## Examples

```ruby
# bad
let(:subject) { foo }
let!(:subject) { foo }
subject(:subject) { foo }
subject!(:subject) { foo }

# bad
block = -> {}
let(:subject, &block)

# good
subject(:test_subject) { foo }
```

## Further Reading

* [RSpec - RSpec/SubjectDeclaration](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecsubjectdeclaration)
