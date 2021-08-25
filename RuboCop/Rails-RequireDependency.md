Pattern: Use of `require_dependency`

Issue: -

## Description

Checks for the usage of `require_dependency`.

`require_dependency` is an obsolete method for Rails applications running in Zeitwerk mode.
In Zeitwerk mode, the semantics should match Ruby's and no need to be defensive with load order,
just refer to classes and modules normally.
If the constant name is dynamic, camelize if needed, and constantize.

Applications running in Zeitwerk mode should not use `require_dependency`.

## Examples

```ruby
# bad
require_dependency 'some_lib'
```

## Further Reading

* [RuboCop - Rails/RequireDependency](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrequiredependency)
