Pattern: Invalid generic type name

Issue: -

## Description

Generic type name should only contain alphanumeric characters, start with an uppercase character and span between 1 and 20 characters in length.

Examples of **correct** code:
```swift
func foo<T>() {}


func foo<T>() -> T {}


func foo<T, U>(param: U) -> T {}


func foo<T: Hashable, U: Rule>(param: U) -> T {}


struct Foo<T> {}


class Foo<T> {}


enum Foo<T> {}


func run(_ options: NoOptions<CommandantError<()>>) {}


func foo(_ options: Set<type>) {}


func < <T: Comparable>(lhs: T?, rhs: T?) -> Bool


func configureWith(data: Either<MessageThread, (project: Project, backing: Backing)>)


typealias StringDictionary<T> = Dictionary<String, T>


typealias BackwardTriple<T1, T2, T3> = (T3, T2, T1)


typealias DictionaryOfStrings<T : Hashable> = Dictionary<T, String>

```
Examples of **incorrect** code:
```swift

func foo<↓T_Foo>() {}


func foo<T, ↓U_Foo>(param: U_Foo) -> T {}


func foo<↓TTTTTTTTTTTTTTTTTTTTT>() {}


func foo<↓type>() {}


typealias StringDictionary<↓T_Foo> = Dictionary<String, T_Foo>


typealias BackwardTriple<T1, ↓T2_Bar, T3> = (T3, T2_Bar, T1)


typealias DictionaryOfStrings<↓T_Foo: Hashable> = Dictionary<T, String>


class Foo<↓T_Foo> {}


class Foo<T, ↓U_Foo> {}


class Foo<↓T_Foo, ↓U_Foo> {}


class Foo<↓TTTTTTTTTTTTTTTTTTTTT> {}


class Foo<↓type> {}


struct Foo<↓T_Foo> {}


struct Foo<T, ↓U_Foo> {}


struct Foo<↓T_Foo, ↓U_Foo> {}


struct Foo<↓TTTTTTTTTTTTTTTTTTTTT> {}


struct Foo<↓type> {}


enum Foo<↓T_Foo> {}


enum Foo<T, ↓U_Foo> {}


enum Foo<↓T_Foo, ↓U_Foo> {}


enum Foo<↓TTTTTTTTTTTTTTTTTTTTT> {}


enum Foo<↓type> {}

```

## Further Reading

* [SwiftLint - Generic Type Name](https://github.com/realm/SwiftLint/blob/master/Rules.md#generic-type-name)