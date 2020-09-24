Pattern: Use of `render text:`

Issue: -

## Description

This cop identifies places where `render text:` can be replaced with `render plain:`.

## Examples

```ruby
# bad - explicit MIME type to `text/plain`
render text: 'Ruby!', content_type: 'text/plain'

# good - short and precise
render plain: 'Ruby!'

# good - explicit MIME type not to `text/plain`
render text: 'Ruby!', content_type: 'text/html'
```

#### ContentTypeCompatibility: true (default)

```ruby
# good - sets MIME type to `text/html`
render text: 'Ruby!'
```

#### ContentTypeCompatibility: false

```ruby
# bad - sets MIME type to `text/html`
render text: 'Ruby!'
```

## Further Reading

* [RuboCop - Rails/RenderPlainText](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrenderplaintext)
