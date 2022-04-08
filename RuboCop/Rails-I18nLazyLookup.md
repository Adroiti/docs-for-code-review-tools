Pattern: Missing use of lazy I18n lookup

Issue: -

## Description

This rule checks for places where I18n "lazy" lookup can be used.

## Examples

```ruby
# en.yml
# en:
#   books:
#     create:
#       success: Book created!

# bad
class BooksController < ApplicationController
  def create
    # ...
    redirect_to books_url, notice: t('books.create.success')
  end
end

# good
class BooksController < ApplicationController
  def create
    # ...
    redirect_to books_url, notice: t('.success')
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Include | `+controllers/**/*+` | Array

## Further Reading

* [Rails - Rails/I18nLazyLookup](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsi18nlazylookup)