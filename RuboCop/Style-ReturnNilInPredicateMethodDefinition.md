Pattern: `return`/`return nil` in predicate method definition

Issue: -

## Description

Checks if `return` or `return nil` is used in predicate method definitions.

## Examples

```ruby
# bad
def foo?
  return if condition

  do_something?
end

# bad
def foo?
  return nil if condition

  do_something?
end

# good
def foo?
  return false if condition

  do_something?
end
```

#### AllowedMethods: ['foo?']

```ruby
# good
def foo?
  return if condition

  do_something?
end
```

#### AllowedPatterns: [/foo/]

```ruby
# good
def foo?
  return if condition

  do_something?
end
```

## Further Reading

* [RuboCop - Style/ReturnNilInPredicateMethodDefinition](https://docs.rubocop.org/rubocop/cops_style.html#stylereturnnilinpredicatemethoddefinition)
* https://rubystyle.guide#bool-methods-qmark