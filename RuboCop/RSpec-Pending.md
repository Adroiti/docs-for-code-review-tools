Pattern: Use of pending/skipped example

Issue: -

## Description

Checks for any pending or skipped examples.

## Examples

```ruby
# bad
describe MyClass do
  it "should be true"
end

describe MyClass do
  it "should be true" do
    pending
  end
end

describe MyClass do
  xit "should be true" do
  end
end

# good
describe MyClass do
end
```

## Further Reading

* [RSpec - RSpec/Pending](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecpending)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Pending](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Pending)
