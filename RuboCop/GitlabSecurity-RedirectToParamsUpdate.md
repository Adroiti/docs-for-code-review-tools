Pattern: Use of `redirect_to(params.update())`

Issue: -

## Description

Check for use of `redirect_to(params.update())`. Passing user params to the `redirect_to method` provides an open redirect.

## Examples

```ruby
# bad
redirect_to(params.update(action:'main'))

# good
redirect_to(whitelist(params))
```

## Further Reading

* [RuboCop - Airbnb/RedirectToParamsUpdate](https://gitlab.com/gitlab-org/rubocop-gitlab-security/-/blob/master/lib/rubocop/cop/gitlab-security/redirect_to_params_update.rb)
