Pattern: Missing empty line after example

Issue: -

## Description

Checks if there is an empty line after example blocks.

## Examples

```ruby
# bad
RSpec.describe Foo do
  it 'does this' do
  end
  it 'does that' do
  end
end

# good
RSpec.describe Foo do
  it 'does this' do
  end

  it 'does that' do
  end
end

# fair - it's ok to have non-separated one-liners
RSpec.describe Foo do
  it { one }
  it { two }
end
```
#### with AllowConsecutiveOneLiners configuration

```ruby
# rubocop.yml
# RSpec/EmptyLineAfterExample:
#   AllowConsecutiveOneLiners: false

# bad
RSpec.describe Foo do
  it { one }
  it { two }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowConsecutiveOneLiners | `true` | Boolean

## Further Reading

* [RSpec - RSpec/EmptyLineAfterExample](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptylineafterexample)
