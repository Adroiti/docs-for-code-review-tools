Pattern: Use of `system("/bin/ls #{params[:file]}")`

Issue: -

## Description

Check for use of `system("/bin/ls #{params[:file]}")`. Passing user input to `system()` without sanitization and parameterization can result in command injection.

## Examples

```ruby
# bad
system("/bin/ls #{filename}")

# good (parameters)
system("/bin/ls", filename)
# even better
exec("/bin/ls", shell_escape(filename))
```

## Further Reading

* [RuboCop - Airbnb/SystemCommandInjection](https://gitlab.com/gitlab-org/rubocop-gitlab-security/-/blob/master/lib/rubocop/cop/gitlab-security/system_command_injection.rb)
