Pattern: Lint/SafeNavigationChain

Issue: -

## Description

The safe navigation operator returns nil if the receiver is
nil.  If you chain an ordinary method call after a safe
navigation operator, it raises NoMethodError.  We should use a
safe navigation operator after a safe navigation operator.
This cop checks for the problem outlined above.

### Example

```ruby
# bad

x&.foo.bar
x&.foo + bar
x&.foo[bar]
```
```ruby
# good

x&.foo&.bar
x&.foo || bar
```

## Default configuration

Attribute | Value
--- | ---
Whitelist | present?, blank?, presence, try

## Further Reading

* [RuboCop - Lint/SafeNavigationChain](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintsafenavigationchain)
