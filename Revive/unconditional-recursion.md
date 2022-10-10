Pattern: Unconditional recursion

Issue: -

## Description

Unconditional recursive calls will produce infinite recursion, thus causing program stack overflow. This rule detects and warns about unconditional (direct) recursive calls.

## Further Reading

* [Revive - unconditional-recursion](https://revive.run/r#unconditional-recursion)