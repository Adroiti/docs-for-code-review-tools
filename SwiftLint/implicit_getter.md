Pattern: Use of implicit getter

Issue: -

## Description

Computed read-only properties should avoid using the `get` keyword.

Examples of **correct** code:
```swift
class Foo {
  var foo: Int {
 get {
 return 3
}
 set {
 _abc = newValue 
}
}
}


class Foo {
  var foo: Int {
 return 20 
} 
}
}


class Foo {
  static var foo: Int {
 return 20 
} 
}
}


class Foo {
  static foo: Int {
 get {
 return 3
}
 set {
 _abc = newValue 
}
}
}


class Foo {
  var foo: Int
}


class Foo {
  var foo: Int {
 return getValueFromDisk() 
} 
}
}


class Foo {
  var foo: String {
 return "get" 
} 
}
}


protocol Foo {
 var foo: Int { get }


protocol Foo {
 var foo: Int { get set }


class Foo {
  var foo: Int {
    struct Bar {
      var bar: Int {
        get { return 1 }
        set { _ = newValue }
      }
    }
    return Bar().bar
  }
}


var _objCTaggedPointerBits: UInt {
   @inline(__always) get { return 0 }
}


var next: Int? {
   mutating get {
       defer { self.count += 1 }
       return self.count
   }
}

```
Examples of **incorrect** code:
```swift

class Foo {
  var foo: Int {
 ↓get {
 return 20 
} 
} 
}
}


class Foo {
  var foo: Int {
 ↓get{
 return 20 
} 
} 
}
}


class Foo {
  static var foo: Int {
 ↓get {
 return 20 
} 
} 
}
}


var foo: Int {
 ↓get {
 return 20 
} 
} 
}


class Foo {
  @objc func bar() { }
var foo: Int {
 ↓get {
 return 20 
} 
} 
}
}

```

## Further Reading

* [SwiftLint - Implicit Getter](https://github.com/realm/SwiftLint/blob/master/Rules.md#implicit-getter)