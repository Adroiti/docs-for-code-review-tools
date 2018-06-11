Pattern: Malformed HTTP status code

Issue: -

## Description

Enforces use of symbolic or numeric value to define HTTP status.

## Examples

#### EnforcedStyle: symbolic (default)

```ruby
# bad
render :foo, status: 200
render json: { foo: 'bar' }, status: 200
render plain: 'foo/bar', status: 304
redirect_to root_url, status: 301

# good
render :foo, status: :ok
render json: { foo: 'bar' }, status: :ok
render plain: 'foo/bar', status: :not_modified
redirect_to root_url, status: :moved_permanently
```
#### EnforcedStyle: numeric

```ruby
# bad
render :foo, status: :ok
render json: { foo: 'bar' }, status: :not_found
render plain: 'foo/bar', status: :not_modified
redirect_to root_url, status: :moved_permanently

# good
render :foo, status: 200
render json: { foo: 'bar' }, status: 404
render plain: 'foo/bar', status: 304
redirect_to root_url, status: 301
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | `symbolic`

## Further Reading

* [RuboCop - Rails/HttpStatus](https://rubocop.readthedocs.io/en/latest/cops_rails/#railshttpstatus)
