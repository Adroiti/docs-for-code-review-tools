Pattern: Use of `remove_const`

Issue: -

## Description

Checks that `remove_const` is not used in specs.

## Examples

```ruby
# bad
it 'does something' do
  Object.send(:remove_const, :SomeConstant)
end

before do
  SomeClass.send(:remove_const, :SomeConstant)
end
```

## Further Reading

* [RSpec - RSpec/RemoveConst](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecremoveconst)
