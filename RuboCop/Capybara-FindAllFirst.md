Pattern: Missing use of `first`

Issue: -

## Description

Enforces use of `first` instead of `all` with `first` or `[0]`.

## Examples

```ruby
# bad
all('a').first
all('a')[0]
find('a', match: :first)
all('a', match: :first)

# good
first('a')
```

## Further Reading

* [Capybara/FindAllFirst](https://docs.rubocop.org/rubocop-capybara/cops_capybara.html#capybarafindallfirst)