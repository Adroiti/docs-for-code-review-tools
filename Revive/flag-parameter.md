Pattern: Use of flag parameter

Issue: -

## Description

If a function controls the flow of another by passing it information on what to do, both functions are said to be [control-coupled](https://en.wikipedia.org/wiki/Coupling_(computer_programming)#Procedural_programming).
Coupling among functions must be minimized for better maintainability of the code.
This rule warns on boolean parameters that create a control coupling.

## Further Reading

* [Revive - flag-parameter](https://revive.run/r#flag-parameter)