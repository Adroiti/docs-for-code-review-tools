Pattern: Circular argument reference

Issue: -

## Description

This rule checks for circular argument references in optional keyword arguments and optional ordinal arguments.

This rule mirrors a warning produced by MRI since 2.2.

## Examples

```ruby
# bad

def bake(pie: pie)
  pie.heat_up
end
```
```ruby
# good

def bake(pie:)
  pie.refrigerate
end
```
```ruby
# good

def bake(pie: self.pie)
  pie.feed_to(user)
end
```
```ruby
# bad

def cook(dry_ingredients = dry_ingredients)
  dry_ingredients.reduce(&:+)
end
```
```ruby
# good

def cook(dry_ingredients = self.dry_ingredients)
  dry_ingredients.combine
end
```

## Further Reading

* [RuboCop - Lint/CircularArgumentReference](https://docs.rubocop.org/rubocop/cops_lint.html#lintcircularargumentreference)
