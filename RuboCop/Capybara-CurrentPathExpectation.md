Pattern: Expectation on `current_path`

Issue: -

## Description

Checks that no expectations are set on Capybara's `current_path`.

The `have_current_path` matcher (http://www.rubydoc.info/github/teamcapybara/capybara/master/Capybara/RSpecMatchers#have_current_path-instance_method) should be used on `page` to set expectations on Capybara's current path, since it uses Capybara's waiting functionality (https://github.com/teamcapybara/capybara/blob/master/README.md#asynchronous-javascript-ajax-and-friends) which ensures that preceding actions (like `click_link`) have completed.

## Examples

```ruby
# bad
expect(current_path).to eq('/callback')
expect(page.current_path).to match(/widgets/)

# good
expect(page).to have_current_path("/callback")
expect(page).to have_current_path(/widgets/)
```

## Further Reading

* [RSpec - Capybara/CurrentPathExpectation](https://docs.rubocop.org/rubocop-rspec/cops_rspec_capybara.html#rspeccapybaracurrentpathexpectations)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/CurrentPathExpectation](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/CurrentPathExpectation)
