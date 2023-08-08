Pattern: Invalid predicate name

Issue: -

## Description

This rule makes sure that predicates are named properly.

## Examples

```ruby
# bad
def is_even?(value) ...

# good
def even?(value)

# bad
def has_value? ...

# good
def value? ...
```

## Default configuration

Attribute | Value
--- | ---
NamePrefix | `is_`, `has_`, `have_`
NamePrefixBlacklist | `is_`, `has_`, `have_`
NameWhitelist | `is_a?`
MethodDefinitionMacros | `define_method`, `define_singleton_method`
Exclude | `spec/**/*`

## Further Reading

* [RuboCop - Naming/PredicateName](https://docs.rubocop.org/rubocop/cops_naming.html#namingpredicatename)
* [https://github.com/bbatsov/ruby-style-guide#bool-methods-qmark](https://github.com/bbatsov/ruby-style-guide#bool-methods-qmark)
