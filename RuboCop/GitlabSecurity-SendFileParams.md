Pattern: Use of `send_file(..., params[], ...)`

Issue: -

## Description

Check for use of `send_file(..., params[], ...)`. Passing user params to the `send_file()` method allows directory traversal.

## Examples

```ruby
# bad
send_file("/tmp/myproj/" + params[:filename])

# good (verify directory)

basename = File.expand_path("/tmp/myproj")
filename = File.expand_path(File.join(basename, @file.public_filename))
raise if basename != filename
send_file filename, disposition: 'inline'
```

## Further Reading

* [RuboCop - Airbnb/SendFileParams](https://gitlab.com/gitlab-org/rubocop-gitlab-security/-/blob/master/lib/rubocop/cop/gitlab-security/send_file_params.rb)
