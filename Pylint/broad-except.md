Pattern: Broad except

Issue: -

## Description

Used when an except catches `Exception` instances. Catching exceptions should be as precise as possible. The type of exceptions that can be raised should be known in advance. Using a catch-all `Exception` instance defeats the purpose of knowing the type of error that occurred, and prohibits the use of tailored responses.

