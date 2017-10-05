Pattern: Malformed parentheses for control statement

Issue: -

## Description

`if`, `for`, `while`, `do` statements shouldn't wrap their conditionals in parentheses.

Examples of **correct** code:
```swift
if condition {


if (a, b) == (0, 1) {


if (a || b) && (c || d) {


if (min...max).contains(value) {


if renderGif(data) {


renderGif(data)


for item in collection {


for (key, value) in dictionary {


for (index, value) in enumerate(array) {


for var index = 0; index < 42; index++ {


guard condition else {


while condition {


} while condition {


do { ; } while condition {


switch foo {

```
Examples of **incorrect** code:
```swift

↓if (condition) {


↓if(condition) {


↓if ((a || b) && (c || d)) {


↓if ((min...max).contains(value)) {


↓for (item in collection) {


↓for (var index = 0; index < 42; index++) {


↓for(item in collection) {


↓for(var index = 0; index < 42; index++) {


↓guard (condition) else {


↓while (condition) {


↓while(condition) {


} ↓while (condition) {


} ↓while(condition) {


do { ; } ↓while(condition) {


do { ; } ↓while (condition) {


↓switch (foo) {

```

## Further Reading

* [SwiftLint - Control Statement](https://github.com/realm/SwiftLint/blob/master/Rules.md#control-statement)