Pattern: Missing use of `Rails.public_path`

Issue: -

## Description

Favor `Rails.public_path` over `Rails.root` with `'public'`

## Examples

```ruby
# bad
Rails.root.join('public')
Rails.root.join('public/file.pdf')
Rails.root.join('public', 'file.pdf')

# good
Rails.public_path
Rails.public_path.join('file.pdf')
Rails.public_path.join('file.pdf')
```
## Further Reading

* [Rails - Rails/RootPublicPath](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrootpublicpath)
