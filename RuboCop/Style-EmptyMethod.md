Pattern: Empty method

Issue: -

## Description

This cop checks for the formatting of empty method definitions.
By default it enforces empty method definitions to go on a single
line (compact style), but it can be configured to enforce the `end`
to go on its own line (expanded style).

Note: A method definition is not considered empty if it contains
      comments.

### Example

```ruby
# EnforcedStyle: compact (default)

# bad
def foo(bar)
end

def self.foo(bar)
end

# good
def foo(bar); end

def foo(bar)
  # baz
end

def self.foo(bar); end
```
```ruby
# EnforcedStyle: expanded

# bad
def foo(bar); end

def self.foo(bar); end

# good
def foo(bar)
end

def self.foo(bar)
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | compact
SupportedStyles | compact, expanded

## Further Reading

* [RuboCop - Style/EmptyMethod](https://rubocop.readthedocs.io/en/latest/cops_style/#styleemptymethod)
* [https://github.com/bbatsov/ruby-style-guide#no-single-line-methods](https://github.com/bbatsov/ruby-style-guide#no-single-line-methods)
