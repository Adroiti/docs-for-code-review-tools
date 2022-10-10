Pattern: Missing use of `time.time.Equal`

Issue: -

## Description

This rule warns when using `==` and `!=` for equality check `time.Time` and suggest to `time.time.Equal` method, for about information follow this [link](https://pkg.go.dev/time#Time).

## Further Reading

* [Revive - time-equal](https://revive.run/r#time-equal)