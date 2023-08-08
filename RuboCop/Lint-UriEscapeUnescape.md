Pattern: Use of `URI.escape`/`URI.unescape`

Issue: -

## Description

This rule identifies places where `URI.escape` can be replaced by
`CGI.escape`, `URI.encode_www_form` or `URI.encode_www_form_component`
depending on your specific use case.
Also this rule identifies places where `URI.unescape` can be replaced by
`CGI.unescape`, `URI.decode_www_form` or `URI.decode_www_form_component`
depending on your specific use case.

## Examples

```ruby
# bad
URI.escape('http://example.com')
URI.encode('http://example.com')

# good
CGI.escape('http://example.com')
URI.encode_www_form('http://example.com')
URI.encode_www_form_component('http://example.com')

# bad
URI.unescape(enc_uri)
URI.decode(enc_uri)

# good
CGI.unescape(enc_uri)
URI.decode_www_form(enc_uri)
URI.decode_www_form_component(enc_uri)
```

## Further Reading

* [RuboCop - Lint/UriEscapeUnescape](https://docs.rubocop.org/rubocop/cops_lint.html#linturiescapeunescape)
