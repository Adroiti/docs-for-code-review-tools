Pattern: Superfluous `disable` command

Issue: -

## Description

SwiftLint `disable` commands are superfluous when the disabled rule would not have triggered a violation in the disabled region.

## Further Reading

* [SwiftLint - Superfluous Disable Command](https://github.com/realm/SwiftLint/blob/master/Rules.md#superfluous-disable-command)