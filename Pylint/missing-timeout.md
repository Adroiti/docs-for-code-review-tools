Pattern: Missing `timeout` parameter

Issue: -

## Description

Used when a method needs a `timeout` parameter in order to avoid waiting for a long time. If no timeout is specified explicitly the default value is used. For example for 'requests' the program will never time out (i.e. hang indefinitely).
