Pattern: Missing use of `fmt.Errorf()`

Issue: -

## Description

It is possible to get a simpler program by replacing `errors.New(fmt.Sprintf())` with `fmt.Errorf()`. This rule spots that kind of simplification opportunities.

## Further Reading

* [Revive - errorf](https://revive.run/r#errorf)