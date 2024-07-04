Pattern: Ambiguous click

Issue: -

## Description

Specify the exact target to click on.

In projects where accessibility needs to be considered, it is crucial to specify the click target precisely.

## Examples

```ruby
# bad
click_link_or_button('foo')
click_on('foo')

# good
click_link('foo')
click_button('foo')
```

## Further Reading

* [Capybara/CurrentPathExpectation](https://docs.rubocop.org/rubocop-capybara/cops_capybara.html#capybaraambiguousclick)