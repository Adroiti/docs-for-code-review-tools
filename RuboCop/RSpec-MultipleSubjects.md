Pattern: Multiple subjects in example group

Issue: -

## Description

Checks if an example group defines `subject` multiple times.

The autocorrect behavior for this rule depends on the type of duplication:

  - If multiple named subjects are defined then this probably indicates
    that the overwritten subjects (all subjects except the last
    definition) are effectively being used to define helpers. In this
    case they are replaced with `let`.

  - If multiple unnamed subjects are defined though then this can *only*
    be dead code and we remove the overwritten subject definitions.

  - If subjects are defined with `subject!` then we don't autocorrect.
    This is enough of an edge case that people can just move this to
    a `before` hook on their own

## Examples

```ruby
# bad
describe Foo do
  subject(:user) { User.new }
  subject(:post) { Post.new }
end

# good
describe Foo do
  let(:user) { User.new }
  subject(:post) { Post.new }
end
```

## Further Reading

* [RSpec - RSpec/MultipleSubjects](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmultiplesubjects)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleSubjects](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleSubjects)
