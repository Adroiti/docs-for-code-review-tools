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

* [RSpec - RSpec/Rails/HaveHttpStatus](https://docs.rubocop.org/rubocop-rspec/cops_rspec_rails.html#rspecrailshavehttpstatus)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Rails/HaveHttpStatus