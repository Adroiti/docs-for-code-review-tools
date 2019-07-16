Pattern: Missing `rel: 'noopener'` for `link_to`

Issue: -

## Description

This cop checks for calls to `link_to` that contain a
`target: '_blank'` but no `rel: 'noopener'`. This can be a security
risk as the loaded page will have control over the previous page
and could change its location for phishing purposes.

### Examples

```ruby
# bad
link_to 'Click here', url, target: '_blank'

# good
link_to 'Click here', url, target: '_blank', rel: 'noopener'
```

## Further Reading

* [RuboCop - Rails/LinkToBlank](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railslinktoblank)
