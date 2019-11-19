Pattern: Invalid file name

Issue: -

## Description

**DO** name source files using `lowercase_with_underscores`.

Some file systems are not case-sensitive, so many projects require filenames to
be all lowercase. Using a separating character allows names to still be readable
in that form. Using underscores as the separator ensures that the name is still
a valid Dart identifier, which may be helpful if the language later supports
symbolic imports.

Example of **correct** code:

* `slider_menu.dart`
* `file_system.dart`

Example of **incorrect** code:

* `SliderMenu.dart`
* `filesystem.dart`
* `file-system.dart`

## Further Reading

* [Linter for Dart - file_names](https://dart-lang.github.io/linter/lints/file_names.html)