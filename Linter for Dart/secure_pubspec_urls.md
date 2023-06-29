Pattern: Missing use of secure URL in `pubspec.yaml`

Issue: -

## Description

**DO** Use secure urls in `pubspec.yaml`.

Use `https` instead of `http` or `git:`.

Example of **correct** code:
```yaml
repository: https://github.com/dart-lang/example
```

Example of **incorrect** code:
```yaml
repository: http://github.com/dart-lang/example
```


## Further Reading

* [Linter for Dart - secure_pubspec_urls](https://dart.dev/tools/linter-rules/secure_pubspec_urls)