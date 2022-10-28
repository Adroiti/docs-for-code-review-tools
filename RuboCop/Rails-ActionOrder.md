Pattern: Wrong Rails controller action order

Issue: -

## Description

Enforces consistent ordering of the standard Rails RESTful controller actions.

The rule is configurable and can enforce any ordering of the standard actions.
All other methods are ignored.

## Examples

```ruby
# bad
def index; end
def destroy; end
def show; end

# good
def index; end
def show; end
def destroy; end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
ExpectedOrder | `index`, `show`, `new`, `edit`, `create`, `update`, `destroy` | Array
Include | `+app/controllers/**/*.rb+` | Array
## Further Reading

* [Rails - Rails/ActionOrder](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactionorder)
