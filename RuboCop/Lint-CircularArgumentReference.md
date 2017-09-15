Pattern: Circular argument reference

Issue: -

## Description

This cop checks for circular argument references in optional keyword arguments and optional ordinal arguments.

This cop mirrors a warning produced by MRI since 2.2.

### Example

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

* [RuboCop - Lint/CircularArgumentReference](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintcircularargumentreference)
