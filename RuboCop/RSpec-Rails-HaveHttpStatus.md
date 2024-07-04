Pattern: Missing use of `have_http_status `

Issue: -

## Description

Checks that tests use `have_http_status` instead of equality matchers.

## Examples

```ruby
# bad
expect(response.status).to be(200)

# good
expect(response).to have_http_status(200)
```

## Further Reading

* [RSpec/Rails/HaveHttpStatus](https://docs.rubocop.org/rubocop-rspec_rails/cops_rspecrails.html#rspecrailshavehttpstatus)