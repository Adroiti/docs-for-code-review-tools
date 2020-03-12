Pattern: Malformed whitespace after opening braces

Issue: -

## Description

Don't include vertical whitespace (empty line) after opening braces.

Examples of **correct** code:
```swift
/*
    class X {

        let x = 5

    }
*/


// [1, 2].map { $0 }.filter { num in


KingfisherManager.shared.retrieveImage(with: url, options: nil, progressBlock: nil) { image, _, _, _ in
    guard let img = image else { return }


[
1,
2,
3
]


[1, 2].map { $0 }.filter { num in


[1, 2].map { $0 }.foo()


class Name {
    run(5) { x in print(x) }
}


class X {
    struct Y {
    class Z {


foo(
x: 5,
y:6
)


if x == 5 {
	print("x is 5")


if x == 5 {
    print("x is 5")


if x == 5 {
    print("x is 5")


if x == 5 {
  print("x is 5")


struct MyStruct {
	let x = 5


struct MyStruct {
    let x = 5


struct MyStruct {
  let x = 5


}) { _ in
    self.dismiss(animated: false, completion: {

```
Examples of **incorrect** code:
```swift

KingfisherManager.shared.retrieveImage(with: url, options: nil, progressBlock: nil) { image, _, _, _ in
↓
    guard let img = image else { return }


[
↓
1,
2,
3
]


class Name {
↓
    run(5) { x in print(x) }
}


class X {
    struct Y {
↓
    class Z {


foo(
↓
x: 5,
y:6
)


if x == 5 {
↓
	print("x is 5")


if x == 5 {
↓

    print("x is 5")


if x == 5 {
↓
    print("x is 5")


if x == 5 {
↓
  print("x is 5")


struct MyStruct {
↓
	let x = 5


struct MyStruct {
↓
    let x = 5


struct MyStruct {
↓
  let x = 5


}) { _ in
↓
    self.dismiss(animated: false, completion: {

```

## Further Reading

* [SwiftLint - Vertical Whitespace after Opening Braces](https://realm.github.io/SwiftLint/vertical_whitespace_opening_braces.html)