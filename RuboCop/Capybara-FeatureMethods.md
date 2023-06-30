Pattern: Inconsistent method usage in feature spec

Issue: -

## Description

Checks for consistent method usage in feature specs.

By default, the cop disables all Capybara-specific methods that have
the same native RSpec method (e.g. are just aliases). Some teams
however may prefer using some of the Capybara methods (like `feature`)
to make it obvious that the test uses Capybara, while still disable
the rest of the methods, like `given` (alias for `let`), `background`
(alias for `before`), etc. You can configure which of the methods to
be enabled by using the EnabledMethods configuration option.

## Examples

```ruby
# bad
feature 'User logs in' do
  given(:user) { User.new }

  background do
    visit new_session_path
  end

  scenario 'with OAuth' do
    # ...
  end
end

# good
describe 'User logs in' do
  let(:user) { User.new }

  before do
    visit new_session_path
  end

  it 'with OAuth' do
    # ...
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnabledMethods | `[]` | Array

## Further Reading

* [RSpec - Capybara/FeatureMethods](https://docs.rubocop.org/rubocop-rspec/cops_rspec_capybara.html#rspeccapybarafeaturemethods)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/FeatureMethods](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/FeatureMethods)
