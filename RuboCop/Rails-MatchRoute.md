Pattern: Use of `match` to define a route

Issue: -

## Description

This rule identifies places where defining routes with match can be replaced with a specific HTTP method.

Don’t use match to define any routes unless there is a need to map multiple request types among [:get, :post, :patch, :put, :delete] to a single action using the `:via` option.

## Examples

```ruby
# bad
match ':controller/:action/:id'
match 'photos/:id', to: 'photos#show', via: :get

# good
get ':controller/:action/:id'
get 'photos/:id', to: 'photos#show'
match 'photos/:id', to: 'photos#show', via: [:get, :post]
match 'photos/:id', to: 'photos#show', via: :all
```

## Further Reading

* [RuboCop - Rails/MatchRoute](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsmatchroute)
