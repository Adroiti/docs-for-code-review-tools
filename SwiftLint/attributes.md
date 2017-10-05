Pattern: Malformed attribute

Issue: -

## Description

Attributes should be on their own lines in functions and types, but on the same line as variables and imports.

Examples of **correct** code:
```swift
@objc var x: String


@objc private var x: String


@nonobjc var x: String


@IBOutlet private var label: UILabel


@IBOutlet @objc private var label: UILabel


@NSCopying var name: NSString


@NSManaged var name: String?


@IBInspectable var cornerRadius: CGFloat


@available(iOS 9.0, *)
 let stackView: UIStackView


@NSManaged func addSomeObject(book: SomeObject)


@IBAction func buttonPressed(button: UIButton)


@objc
 @IBAction func buttonPressed(button: UIButton)


@available(iOS 9.0, *)
 func animate(view: UIStackView)


@available(iOS 9.0, *, message="A message")
 func animate(view: UIStackView)


@nonobjc
 final class X


@available(iOS 9.0, *)
 class UIStackView


@NSApplicationMain
 class AppDelegate: NSObject, NSApplicationDelegate


@UIApplicationMain
 class AppDelegate: NSObject, UIApplicationDelegate


@IBDesignable
 class MyCustomView: UIView


@testable import SourceKittenFramework


@objc(foo_x)
 var x: String


@available(iOS 9.0, *)
@objc(abc_stackView)
 let stackView: UIStackView


@objc(abc_addSomeObject:)
 @NSManaged func addSomeObject(book: SomeObject)


@objc(ABCThing)
 @available(iOS 9.0, *)
 class Thing


class Foo: NSObject {
 override var description: String { return "" }
}


class Foo: NSObject {

 override func setUp() {}
}


@objc
class ⽺ {}


extension Property {

 @available(*, unavailable, renamed: "isOptional")
public var optional: Bool { fatalError() }
}


@GKInspectable var maxSpeed: Float


@discardableResult
 func a() -> Int


@objc
 @discardableResult
 func a() -> Int


func increase(f: @autoclosure () -> Int) -> Int


func foo(completionHandler: @escaping () -> Void)

```
Examples of **incorrect** code:
```swift

@objc
 ↓var x: String


@objc

 ↓var x: String


@objc
 private ↓var x: String


@nonobjc
 ↓var x: String


@IBOutlet
 private ↓var label: UILabel


@IBOutlet

 private ↓var label: UILabel


@NSCopying
 ↓var name: NSString


@NSManaged
 ↓var name: String?


@IBInspectable
 ↓var cornerRadius: CGFloat


@available(iOS 9.0, *) ↓let stackView: UIStackView


@NSManaged
 ↓func addSomeObject(book: SomeObject)


@IBAction
 ↓func buttonPressed(button: UIButton)


@IBAction
 @objc
 ↓func buttonPressed(button: UIButton)


@available(iOS 9.0, *) ↓func animate(view: UIStackView)


@nonobjc final ↓class X


@available(iOS 9.0, *) ↓class UIStackView


@available(iOS 9.0, *)
 @objc ↓class UIStackView


@available(iOS 9.0, *) @objc
 ↓class UIStackView


@available(iOS 9.0, *)

 ↓class UIStackView


@UIApplicationMain ↓class AppDelegate: NSObject, UIApplicationDelegate


@IBDesignable ↓class MyCustomView: UIView


@testable
↓import SourceKittenFramework


@testable


↓import SourceKittenFramework


@objc(foo_x) ↓var x: String


@available(iOS 9.0, *) @objc(abc_stackView)
 ↓let stackView: UIStackView


@objc(abc_addSomeObject:) @NSManaged
 ↓func addSomeObject(book: SomeObject)


@objc(abc_addSomeObject:)
 @NSManaged
 ↓func addSomeObject(book: SomeObject)


@available(iOS 9.0, *)
 @objc(ABCThing) ↓class Thing


@GKInspectable
 ↓var maxSpeed: Float


@discardableResult ↓func a() -> Int


@objc
 @discardableResult ↓func a() -> Int


@objc

 @discardableResult
 ↓func a() -> Int

```

## Further Reading

* [SwiftLint - Attributes](https://github.com/realm/SwiftLint/blob/master/Rules.md#attributes)