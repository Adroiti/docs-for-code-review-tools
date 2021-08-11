Pattern: Missing empty line after hook

Issue: -

## Description

Checks if there is an empty line after hook blocks.

## Examples

```ruby
# bad
before { do_something }
it { does_something }

# bad
after { do_something }
it { does_something }

# bad
around { |test| test.run }
it { does_something }

# good
before { do_something }

it { does_something }

# good
after { do_something }

it { does_something }

# good
around { |test| test.run }

it { does_something }
```

## Further Reading

* [RSpec - RSpec/EmptyLineAfterHook](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptylineafterhook)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterHook](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterHook)
