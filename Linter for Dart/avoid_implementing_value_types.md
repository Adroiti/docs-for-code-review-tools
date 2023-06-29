Pattern: Implementing class which overrides `==`

Issue: -

## Description

The `==` operator is contractually required to be an equivalence relation;
that is, symmetrically for all objects `o1` and `o2`, `o1 == o2` and `o2 == o1`
must either both be true, or both be false.

> _NOTE_: Dart does not have true _value types_, so instead we consider a class
> that implements `==` as a _proxy_ for identifying value types.

When using `implements`, you do not inherit the method body of `==`, making it
nearly impossible to follow the contract of `==`. Classes that override `==`
typically are usable directly in tests _without_ creating mocks or fakes as
well. For example, for a given class `Size`:

```
class Size {
 final int inBytes;
 const Size(this.inBytes);

 @override
 bool operator ==(Object other) => other is Size && other.inBytes == inBytes;

 @override
 int get hashCode => inBytes.hashCode;
}
```

Example of **incorrect** code:
```
class CustomSize implements Size {
 final int inBytes;
 const CustomSize(this.inBytes);

 int get inKilobytes => inBytes ~/ 1000;
}
```

Example of **incorrect** code:
```
import 'package:test/test.dart';
import 'size.dart';

class FakeSize implements Size {
 int inBytes = 0;
}

void main() {
 test('should not throw on a size >1Kb', () {
  expect(() => someFunction(FakeSize()..inBytes = 1001), returnsNormally);
 });
}
```

Example of **correct** code:
```
class ExtendedSize extends Size {
 ExtendedSize(int inBytes) : super(inBytes);

 int get inKilobytes => inBytes ~/ 1000;
}
```

Example of **correct** code:
```
import 'package:test/test.dart';
import 'size.dart';

void main() {
 test('should not throw on a size >1Kb', () {
  expect(() => someFunction(new Size(1001)), returnsNormally);
 });
}
```

## Further Reading

* [Linter for Dart - avoid_implementing_value_types](https://dart.dev/tools/linter-rules/avoid_implementing_value_types)