Pattern: Disabled deep munge

Issue: -

## Description

Checks for disabling the deep munge security control.  Disabling this security setting can leave the application open to unsafe query generation.

## Examples

```ruby
# bad
config.action_dispatch.perform_deep_munge = false
```

## Further Reading

* [RuboCop - Airbnb/DeepMunge](https://gitlab.com/gitlab-org/rubocop-gitlab-security/-/blob/master/lib/rubocop/cop/gitlab-security/deep_munge.rb)
