Pattern: Redundant unittest assert

Issue: -

## Description

The first argument of assertTrue and assertFalse is a condition. If a constant is passed as parameter, that condition will be always true. In this case a warning should be emitted.