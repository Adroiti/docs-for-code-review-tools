Pattern: Misplaced bare raise

Issue: -

## Description

Used when a bare raise is not used inside an except clause. This generates an error, since there are no active exceptions to be reraised. An exception to this rule is represented by a bare raise inside a finally clause, which might work, as long as an exception is raised inside the try block, but it is nevertheless a code smell that must not be relied upon.