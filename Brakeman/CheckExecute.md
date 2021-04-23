Pattern: Possible command injection

Issue: -

## Description

Checks for string interpolation and parameters in calls to `Kernel#system`, `Kernel#exec`, `Kernel#syscall`, and inside backticks.

Examples of command injection vulnerabilities:

```ruby
system("rf -rf #{params[:file]}")
exec(params[:command])
unlink #{params[:something}
```

## Further Reading

* [Brakeman - Command Injection](https://brakemanscanner.org/docs/warning_types/command_injection/)