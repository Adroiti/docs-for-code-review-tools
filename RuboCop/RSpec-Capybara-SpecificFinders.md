Pattern: Missing use of specific finder by Capybara

Issue: -

## Description

Checks if there is a more specific finder offered by Capybara.

## Examples

```ruby
# bad
find('#some-id')
find('[visible][id=some-id]')

# good
find_by_id('some-id')
find_by_id('some-id', visible: true)
```

## Further Reading

* [RSpec - RSpec/Capybara/SpecificFinders](https://docs.rubocop.org/rubocop-rspec/cops_rspec_capybara.html#rspeccapybaraspecificfinders)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/SpecificFinders