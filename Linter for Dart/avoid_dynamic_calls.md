Pattern: Use of dynamic call

Issue: -

## Description

**DO** avoid method calls or accessing properties on an object that is either explicitly or implicitly statically typed "dynamic". Dynamic calls are treated slightly different in every runtime environment and compiler, but most production modes (and even some development modes) have both compile size and runtime performance penalties associated with dynamic calls.

Additionally, targets typed "dynamic" disables most static analysis, meaning it is easier to lead to a runtime "NoSuchMethodError" or "NullError" than properly statically typed Dart code.

There is an exception to methods and properties that exist on "Object?":

    a.hashCode
    a.runtimeType
    a.noSuchMethod(someInvocation)
    a.toString()

... these members are dynamically dispatched in the web-based runtimes, but not in the VM-based ones. Additionally, they are so common that it would be very punishing to disallow `any.toString()` or `any == true`, for example.

Note that despite "Function" being a type, the semantics are close to identical to "dynamic", and calls to an object that is typed "Function" will also trigger this lint.

Example of **incorrect** code:

```dart
void explicitDynamicType(dynamic object) {
  print(object.foo());
}

void implicitDynamicType(object) {
  print(object.foo());
}

abstract class SomeWrapper {
  T doSomething<T>();
}

void inferredDynamicType(SomeWrapper wrapper) {
  var object = wrapper.doSomething();
  print(object.foo());
}

void callDynamic(dynamic function) {
  function();
}

void functionType(Function function) {
  function();
}
```

Example of **correct** code:

```dart
void explicitType(Fooable object) {
  object.foo();
}

void castedType(dynamic object) {
  (object as Fooable).foo();
}

abstract class SomeWrapper {
  T doSomething<T>();
}

void inferredType(SomeWrapper wrapper) {
  var object = wrapper.doSomething<Fooable>();
  object.foo();
}

void functionTypeWithParameters(Function() function) {
  function();
}
```


## Further Reading

* [Linter for Dart - avoid_dynamic_calls](https://dart.dev/tools/linter-rules/avoid_dynamic_calls)