Pattern: Use of `have_selector`

Issue: -

## Description

Use `have_css` or `have_xpath instead` of `have_selector`.

## Examples

```ruby
# bad
expect(foo).to have_selector(:css, 'bar')

# good
expect(foo).to have_css('bar')

# bad
expect(foo).to have_selector(:xpath, 'bar')

# good
expect(foo).to have_xpath('bar')
```

## Further Reading

* [Capybara/RSpec/HaveSelector](https://docs.rubocop.org/rubocop-capybara/cops_capybara_rspec.html#capybararspechaveselector)