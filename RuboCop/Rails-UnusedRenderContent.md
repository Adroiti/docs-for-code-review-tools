Pattern: Unused `render` content

Issue: -

## Description

If you try to render content along with a non-content status code (100-199, 204, 205, or 304), it will be dropped from the response.

This rule checks for uses of `render` which specify both body content and a non-content status.

## Examples

```ruby
# bad
render 'foo', status: :continue
render status: 100, plain: 'Ruby!'

# good
head :continue
head 100
```

## Further Reading

* [RuboCop - Rails/UnusedRenderContent](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsunusedrendercontent)
