Pattern: Invalid library name

Issue: -

## Description

**DO** name libraries using `lowercase_with_underscores`.

Some file systems are not case-sensitive, so many projects require filenames to
be all lowercase. Using a separating character allows names to still be readable
in that form. Using underscores as the separator ensures that the name is still
a valid Dart identifier, which may be helpful if the language later supports
symbolic imports.

Example of **correct** code:

* `library peg_parser;`

Example of **incorrect** code:

* `library peg-parser;`

## Further Reading

* [Linter for Dart - library_names](https://dart.dev/tools/linter-rules/library_names)