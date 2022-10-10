Pattern: Suspicious range variable assignment

Issue: -

## Description

Range variables in a loop are reused at each iteration. This rule warns when assigning the address of the variable, passing the address to `append()` or using it in a map.

## Further Reading

* [Revive - range-val-address](https://revive.run/r#range-val-address)