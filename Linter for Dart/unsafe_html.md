Pattern: Use of unsafe HTML API

Issue: -

## Description

**AVOID** assigning directly to the `src` field of an `EmbedElement`, `IFrameElement`, `ImageElement`, or `ScriptElement`, or the `href` field of an `AnchorElement`.

Example of **incorrect** code:
```dart
var script = ScriptElement()..src = 'foo.js';
```

## Further Reading

* [Linter for Dart - unsafe_html](https://dart-lang.github.io/linter/lints/unsafe_html.html)