Pattern: Missing use of `have_no_*`/`not_to`

Issue: -

## Description

Enforces use of `have_no_*` or `not_to` for negated expectations.

## Examples

#### EnforcedStyle: not_to (default)

```ruby
# bad
expect(page).to have_no_selector
expect(page).to have_no_css('a')

# good
expect(page).not_to have_selector
expect(page).not_to have_css('a')
```

#### EnforcedStyle: have_no

```ruby
# bad
expect(page).not_to have_selector
expect(page).not_to have_css('a')

# good
expect(page).to have_no_selector
expect(page).to have_no_css('a')
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `not_to` | `have_no`, `not_to`

## Further Reading

* [RSpec - RSpec/Capybara/NegationMatcher](https://docs.rubocop.org/rubocop-rspec/cops_rspec_capybara.html#rspeccapybaranegationmatcher)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/NegationMatcher