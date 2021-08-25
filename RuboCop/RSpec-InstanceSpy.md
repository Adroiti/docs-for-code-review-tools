Pattern: Missing use of `instance_spy`

Issue: -

## Description

Checks for `instance_double` used with `have_received`.

## Examples

```ruby
# bad
it do
  foo = instance_double(Foo).as_null_object
  expect(foo).to have_received(:bar)
end

# good
it do
  foo = instance_spy(Foo)
  expect(foo).to have_received(:bar)
end
```

## Further Reading

* [RSpec - RSpec/InstanceSpy](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecinstancespy)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InstanceSpy](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InstanceSpy)
