Pattern: Misused `around` block

Issue: -

## Description

Checks that `around` blocks actually run the test.

## Examples

```ruby
# bad
around do
  some_method
end

around do |test|
  some_method
end

# good
around do |test|
  some_method
  test.call
end

around do |test|
  some_method
  test.run
end
```

## Further Reading

* [RSpec - RSpec/AroundBlock](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecaroundblock)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AroundBlock](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AroundBlock)
