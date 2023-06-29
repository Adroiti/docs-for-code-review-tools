Pattern: Invalid package name

Issue: -

## Description

Package names should be all lowercase, with underscores to separate words,
`just_like_this`. Use only basic Latin letters and Arabic digits: [a-z0-9_].
Also, make sure the name is a valid Dart identifier -- that it doesn't start
with digits and isn't a reserved word.

## Further Reading

* [Linter for Dart - package_names](https://dart.dev/tools/linter-rules/package_names)
* [Pubspec format description](https://www.dartlang.org/tools/pub/pubspec.html)