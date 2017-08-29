Pattern: Taking an address of a cast

Issue: -

## Description

This is dangerous: could be a temp var. Take the address before doing the cast, rather than after.