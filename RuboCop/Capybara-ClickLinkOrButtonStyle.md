Pattern: Inconsistent button/link click style

Issue: -

## Description

Checks for methods of button or link clicks.

This cop is deprecated. We plan to remove this in the next major version update to 3.0.


## Examples

```ruby
# bad
# bad
click_link('foo')
click_button('foo')

# good
click_link_or_button('foo')
click_on('foo')
```

## Further Reading

* [Capybara/ClickLinkOrButtonStyle](https://docs.rubocop.org/rubocop-capybara/cops_capybara.html#capybaraclicklinkorbuttonstyle)