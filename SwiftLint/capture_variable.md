Pattern: Use of `var` in closure's capture list

Issue: -

## Description

Non-constant variables should not be listed in a closure’s capture list to avoid confusion about closures capturing variables at creation time.

Examples of **correct** code:

```swift
class C {
    let i: Int
    init(_ i: Int) { self.i = i }
}

let j: Int = 0
let c = C(1)

let closure: () -> Void = { [j, c] in
    print(c.i, j)
}

closure()

let iGlobal: Int = 0

class C {
    class var iClass: Int { 0 }
    static let iStatic: Int = 0
    let iInstance: Int = 0

    func callTest() {
        var iLocal: Int = 0
        test { [unowned self, iGlobal, iInstance, iLocal, iClass=C.iClass, iStatic=C.iStatic] j in
            print(iGlobal, iClass, iStatic, iInstance, iLocal, j)
        }
    }

    func test(_ completionHandler: @escaping (Int) -> Void) {
    }
}

var j: Int!
j = 0

let closure: () -> Void = { [j] in
    print(j)
}

closure()
j = 1
closure()

lazy var j: Int = { 0 }()

let closure: () -> Void = { [j] in
    print(j)
}

closure()
j = 1
closure()

```

Examples of **incorrect** code:

```swift
var j: Int = 0

let closure: () -> Void = { [j] in
    print(j)
}

closure()
j = 1
closure()

class C {
    let i: Int
    init(_ i: Int) { self.i = i }
}

var c = C(0)
let closure: () -> Void = { [c] in
    print(c.i)
}

closure()
c = C(1)
closure()

var iGlobal: Int = 0

class C {
    func callTest() {
        test { [iGlobal] j in
            print(iGlobal, j)
        }
    }

    func test(_ completionHandler: @escaping (Int) -> Void) {
    }
}

class C {
    class var iClass: Int {
        get { iStatic }
        set { iStatic = newValue }
    }
    static var iStatic: Int = 0

    func callTest() {
        test { [iClass=C.iClass] j in
            print(iClass, j)
        }
    }

    func test(_ completionHandler: @escaping (Int) -> Void) {
    }
}

class C {
    static var iStatic: Int = 0

    static func callTest() {
        test { [iStatic] j in
            print(iStatic, j)
        }
    }

    static func test(_ completionHandler: @escaping (Int) -> Void) {
        completionHandler(2)
        C.iStatic = 1
        completionHandler(3)
    }
}

C.callTest()

class C {
    var iInstance: Int = 0

    func callTest() {
        test { [iInstance] j in
            print(iInstance, j)
        }
    }

    func test(_ completionHandler: @escaping (Int) -> Void) {
    }
}

```

## Further Reading

* [SwiftLint - Capture Variable](https://realm.github.io/SwiftLint/capture_variable.html)