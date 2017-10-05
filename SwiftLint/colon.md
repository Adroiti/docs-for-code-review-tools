Pattern: Malformed `:`

Issue: -

## Description

Colons should be next to the identifier when specifying a type and next to the key in dictionary literals.

Examples of **correct** code:
```swift
let abc: Void


let abc: [Void: Void]


let abc: (Void, Void)


let abc: ([Void], String, Int)


let abc: [([Void], String, Int)]


let abc: String="def"


let abc: Int=0


let abc: Enum=Enum.Value


func abc(def: Void) {}


func abc(def: Void, ghi: Void) {}


// 周斌佳年周斌佳
let abc: String = "abc:"


let abc = [Void: Void]()


let abc = [1: [3: 2], 3: 4]


let abc = ["string": "string"]


let abc = ["string:string": "string"]


let abc: [String: Int]


func foo(bar: [String: Int]) {}


func foo() -> [String: Int] { return [:] }


let abc: Any


let abc: [Any: Int]


let abc: [String: Any]


class Foo: Bar {}


class Foo<T: Equatable> {}


switch foo {
case .bar:
    _ = something()
}


object.method(x: 5, y: "string")


object.method(x: 5, y:
              "string")


object.method(5, y: "string")

```
Examples of **incorrect** code:
```swift

let ↓abc:Void


let ↓abc:  Void


let ↓abc :Void


let ↓abc : Void


let ↓abc : [Void: Void]


let ↓abc : (Void, String, Int)


let ↓abc : ([Void], String, Int)


let ↓abc : [([Void], String, Int)]


let ↓abc:  (Void, String, Int)


let ↓abc:  ([Void], String, Int)


let ↓abc:  [([Void], String, Int)]


let ↓abc :String="def"


let ↓abc :Int=0


let ↓abc :Int = 0


let ↓abc:Int=0


let ↓abc:Int = 0


let ↓abc:Enum=Enum.Value


func abc(↓def:Void) {}


func abc(↓def:  Void) {}


func abc(↓def :Void) {}


func abc(↓def : Void) {}


func abc(def: Void, ↓ghi :Void) {}


let abc = [Void↓:Void]()


let abc = [Void↓ : Void]()


let abc = [Void↓:  Void]()


let abc = [Void↓ :  Void]()


let abc = [1: [3↓ : 2], 3: 4]


let abc = [1: [3↓ : 2], 3↓:  4]


let abc: [↓String : Int]


let abc: [↓String:Int]


func foo(bar: [↓String : Int]) {}


func foo(bar: [↓String:Int]) {}


func foo() -> [↓String : Int] { return [:] }


func foo() -> [↓String:Int] { return [:] }


let ↓abc : Any


let abc: [↓Any : Int]


let abc: [↓String : Any]


class ↓Foo : Bar {}


class ↓Foo:Bar {}


class Foo<↓T:Equatable> {}


class Foo<↓T : Equatable> {}


object.method(x: 5, y↓ : "string")


object.method(x↓:5, y: "string")


object.method(x↓:  5, y: "string")

```

## Further Reading

* [SwiftLint - Colon](https://github.com/realm/SwiftLint/blob/master/Rules.md#colon)