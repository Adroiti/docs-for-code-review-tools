Pattern: Missing use of `throwsA` matcher

Issue: -

## Description

Use the `throwsA` matcher instead of try-catch with `fail()`.

Example of **incorrect** code:


```dart
// sync code
try {
 someSyncFunctionThatThrows();
 fail('expected Error');
} on Error catch (error) {
 expect(error.message, contains('some message'));
}

// async code
try {
 await someAsyncFunctionThatThrows();
 fail('expected Error');
} on Error catch (error) {
 expect(error.message, contains('some message'));
}
```

Example of **correct** code:

```dart
// sync code
expect(
 () => someSyncFunctionThatThrows(),
 throwsA(isA<Error>().having((Error error) => error.message, 'message', contains('some message'))),
);

// async code
await expectLater(
 () => someAsyncFunctionThatThrows(),
 throwsA(isA<Error>().having((Error error) => error.message, 'message', contains('some message'))),
);
```

## Further Reading

* [Linter for Dart - use_test_throws_matchers](https://dart.dev/tools/linter-rules/use_test_throws_matchers)