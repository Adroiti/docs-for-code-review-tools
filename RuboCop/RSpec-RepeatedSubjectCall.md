Pattern: Repeated call to memoized subject

Issue: -

## Description

Checks for repeated calls to subject missing that it is memoized.

## Examples

```ruby
# bad
it do
  subject
  expect { subject }.to not_change { A.count }
end

it do
  expect { subject }.to change { A.count }
  expect { subject }.to not_change { A.count }
end

# good
it do
  expect { my_method }.to change { A.count }
  expect { my_method }.to not_change { A.count }
end

# also good
it do
  expect { subject.a }.to change { A.count }
  expect { subject.b }.to not_change { A.count }
end
```

## Further Reading

* [RSpec - RSpec/RepeatedSubjectCall](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecrepeatedsubjectcall)