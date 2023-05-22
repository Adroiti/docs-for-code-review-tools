Pattern: Missing use of Capybara-specific action

Issue: -

## Description

Checks for there is a more specific actions offered by Capybara.

## Examples

```ruby
# bad
find('a').click
find('button.cls').click
find('a', exact_text: 'foo').click
find('div button').click

# good
click_link
click_button(class: 'cls')
click_link(exact_text: 'foo')
find('div').click_button
```

## Further Reading

* [RSpec - RSpec/Capybara/SpecificActions](https://docs.rubocop.org/rubocop-rspec/cops_rspec_capybara.html#rspeccapybaraspecificactions)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/SpecificActions