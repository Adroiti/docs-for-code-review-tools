Pattern: Use of inline rendering

Issue: -

## Description

This rule looks for inline rendering within controller actions.

## Examples

```ruby
# bad
class ProductsController < ApplicationController
  def index
    render inline: "<% products.each do |p| %><p><%= p.name %></p><% end %>", type: :erb
  end
end

# good
# app/views/products/index.html.erb
# <% products.each do |p| %>
#   <p><%= p.name %></p>
# <% end %>

class ProductsController < ApplicationController
  def index
  end
end
```

## Further Reading

* [RuboCop - Rails/RenderInline](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrenderinline)
