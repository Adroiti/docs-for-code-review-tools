Pattern: Use of force unwrapping

Issue: -

## Description

Force unwrapping should be avoided.

Examples of **correct** code:
```swift
if let url = NSURL(string: query)


navigationController?.pushViewController(viewController, animated: true)


let s as! Test


try! canThrowErrors()


let object: Any!


@IBOutlet var constraints: [NSLayoutConstraint]!


setEditing(!editing, animated: true)


navigationController.setNavigationBarHidden(!navigationController.navigationBarHidden, animated: true)


if addedToPlaylist && (!self.selectedFilters.isEmpty || self.searchBar?.text?.isEmpty == false) {}


print("\(xVar)!")


var test = (!bar)


var a: [Int]!


private var myProperty: (Void -> Void)!


func foo(_ options: [AnyHashable: Any]!) {

```
Examples of **incorrect** code:
```swift

let url = NSURL(string: query)↓!


navigationController↓!.pushViewController(viewController, animated: true)


let unwrapped = optional↓!


return cell↓!


let url = NSURL(string: "http://www.google.com")↓!


let dict = ["Boooo": "👻"]func bla() -> String { return dict["Boooo"]↓! }


let dict = ["Boooo": "👻"]func bla() -> String { return dict["Boooo"]↓!.contains("B") }


let a = dict["abc"]↓!.contains("B")


dict["abc"]↓!.bar("B")


if dict["a"]↓!!!! {


var foo: [Bool]! = dict["abc"]↓!


context("abc") {
  var foo: [Bool]! = dict["abc"]↓!
}


open var computed: String { return foo.bar↓! }

```

## Further Reading

* [SwiftLint - Force Unwrapping](https://github.com/realm/SwiftLint/blob/master/Rules.md#force-unwrapping)