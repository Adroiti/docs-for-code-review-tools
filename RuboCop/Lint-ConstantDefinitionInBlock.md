Pattern: Constant definition in block

Issue: -

## Description

Do not define constants within a block, since the block's scope does not
isolate or namespace the constant in any way.

If you are trying to define that constant once, define it outside of
the block instead, or use a variable or method if defining the constant
in the outer scope would be problematic.

For meta-programming, use `const_set`.

## Examples

```ruby
# bad
task :lint do
  FILES_TO_LINT = Dir['lib/*.rb']
end

# bad
describe 'making a request' do
  class TestRequest; end
end

# bad
module M
  extend ActiveSupport::Concern
  included do
    LIST = []
  end
end

# good
task :lint do
  files_to_lint = Dir['lib/*.rb']
end

# good
describe 'making a request' do
  let(:test_request) { Class.new }
  # see also `stub_const` for RSpec
end

# good
module M
  extend ActiveSupport::Concern
  included do
    const_set(:LIST, [])
  end
end
```

## Further Reading

* [RuboCop - Lint/ConstantDefinitionInBlock](https://docs.rubocop.org/rubocop/cops_lint.html#lintconstantdefinitioninblock)
* [The Ruby Style Guide](https://rubystyle.guide#no-constant-definition-in-block)