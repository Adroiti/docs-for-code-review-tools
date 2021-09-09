Pattern: Use of `where("name = '#{params[:name]}'")`

Issue: -

## Description

Check for use of `where("name = '#{params[:name]}'")`. Passing user input to `where()` without parameterization can result in SQL Injection.

## Examples

```ruby
# bad
u = User.where("name = '#{params[:name]}'")

# good (parameters)
u = User.where("name = ? AND id = ?", params[:name], params[:id])
u = User.where(name: params[:name], id: params[:id])
```

## Further Reading

* [RuboCop - Airbnb/SqlInjection](https://gitlab.com/gitlab-org/rubocop-gitlab-security/-/blob/master/lib/rubocop/cop/gitlab-security/sql_injection.rb)
