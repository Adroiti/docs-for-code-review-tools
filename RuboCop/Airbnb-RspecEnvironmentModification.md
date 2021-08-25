Pattern: Missing use of `stub_env`

Issue: -

## Description

Checks how the Rails environment is modified in specs. If an individual method on Rails.env is modified multiple environment related branches could be run down. Rather than modifying a single path or setting Rails.env in a way that could bleed into other specs, use `stub_env`.

## Examples

```ruby
# bad

# spec/foo/bar_spec.rb
before(:each) do
  allow(Rails.env).to receive(:production).and_return(true)
end

before(:each) do
  expect(Rails.env).to receive(:production).and_return(true)
end

before(:each) do
  Rails.env = :production
end

# good

# spec/foo/bar_spec.rb do
before(:each) do
  stub_env(:production)
end
```

## Further Reading

* [RuboCop - Airbnb/RspecEnvironmentModification](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/rspec_environment_modification.rb)
