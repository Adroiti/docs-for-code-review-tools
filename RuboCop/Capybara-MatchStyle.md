Pattern: Use of deprecated style method

Issue: -

## Description

Checks for usage of deprecated style methods.

## Examples

#### when using `assert_style`

```ruby
# bad
page.find(:css, '#first').assert_style(display: 'block')

# good
page.find(:css, '#first').assert_matches_style(display: 'block')
```

#### when using `has_style?`

```ruby
# bad
expect(page.find(:css, 'first')
  .has_style?(display: 'block')).to be true

# good
expect(page.find(:css, 'first')
  .matches_style?(display: 'block')).to be true
```

#### when using `have_style`

```ruby
# bad
expect(page).to have_style(display: 'block')

# good
expect(page).to match_style(display: 'block')
```

## Further Reading

* [Capybara/MatchStyle](* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Capybara/MatchStyle)