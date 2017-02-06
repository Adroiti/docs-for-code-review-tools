Pattern: Cell var from loop

Issue: -

## Description

A variable used in a closure is defined in a loop. This will result in all closures using the same value for the closed-over variable.