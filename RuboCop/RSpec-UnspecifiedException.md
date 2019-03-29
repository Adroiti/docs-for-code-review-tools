Pattern: Unspecified exception

Issue: -

## Description

Checks for a specified error in checking raised errors.

Enforces one of an Exception type, a string, or a regular
expression to match against the exception message as a parameter
to `raise_error`

## Examples

```ruby
# bad
expect {
  raise StandardError.new('error')
}.to raise_error

# good
expect {
  raise StandardError.new('error')
}.to raise_error(StandardError)

expect {
  raise StandardError.new('error')
}.to raise_error('error')

expect {
  raise StandardError.new('error')
}.to raise_error(/err/)

expect { do_something }.not_to raise_error
```

## Further Reading

* [RSpec - RSpec/UnspecifiedException](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecunspecifiedexception)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/UnspecifiedException](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/UnspecifiedException)
