Pattern: Use of compound hash

Issue: -

## Description

This rule checks for implementations of the `hash` method which combine
values using custom logic instead of delegating to `Array#hash`.

Manually combining hashes is error prone and hard to follow, especially
when there are many values. Poor implementations may also introduce
performance or security concerns if they are prone to collisions.
Delegating to `Array#hash` is clearer, faster, and safer.

## Examples

```ruby
# bad
def hash
  @foo ^ @bar
end

# good
def hash
  [@foo, @bar].hash
end
```

## Further Reading

* [RuboCop - Security/CompoundHash](https://docs.rubocop.org/rubocop/cops_security.html#securitycompoundhash)
