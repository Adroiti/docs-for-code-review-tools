Pattern: Unclear visibility in capybara finder

Issue: -

## Description

Checks for boolean visibility in capybara finders.

Capybara lets you find elements that match a certain visibility using
the `:visible` option. `:visible` accepts both boolean and symbols as
values, however using booleans can have unwanted effects. `visible:
false` does not find just invisible elements, but both visible and
invisible elements. For expressiveness and clarity, use one of the
symbol values, `:all`, `:hidden` or `:visible`.

## Examples

```ruby
# bad
expect(page).to have_selector('.foo', visible: false)

# bad
expect(page).to have_selector('.foo', visible: true)

# good
expect(page).to have_selector('.foo', visible: :all)

# good
expect(page).to have_selector('.foo', visible: :hidden)

# good
expect(page).to have_selector('.foo', visible: :visible)
```

## Further Reading

* [Capybara/VisibilityMatcher](https://docs.rubocop.org/rubocop-capybara/cops_capybara.html#capybaravisibilitymatcher)
