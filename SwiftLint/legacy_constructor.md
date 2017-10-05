Pattern: Use of legacy constructor

Issue: -

## Description

Swift constructors are preferred over legacy convenience functions.

Examples of **correct** code:
```swift
CGPoint(x: 10, y: 10)


CGPoint(x: xValue, y: yValue)


CGSize(width: 10, height: 10)


CGSize(width: aWidth, height: aHeight)


CGRect(x: 0, y: 0, width: 10, height: 10)


CGRect(x: xVal, y: yVal, width: aWidth, height: aHeight)


CGVector(dx: 10, dy: 10)


CGVector(dx: deltaX, dy: deltaY)


NSPoint(x: 10, y: 10)


NSPoint(x: xValue, y: yValue)


NSSize(width: 10, height: 10)


NSSize(width: aWidth, height: aHeight)


NSRect(x: 0, y: 0, width: 10, height: 10)


NSRect(x: xVal, y: yVal, width: aWidth, height: aHeight)


NSRange(location: 10, length: 1)


NSRange(location: loc, length: len)


UIEdgeInsets(top: 0, left: 0, bottom: 10, right: 10)


UIEdgeInsets(top: aTop, left: aLeft, bottom: aBottom, right: aRight)


NSEdgeInsets(top: 0, left: 0, bottom: 10, right: 10)


NSEdgeInsets(top: aTop, left: aLeft, bottom: aBottom, right: aRight)

```
Examples of **incorrect** code:
```swift

↓CGPointMake(10, 10)


↓CGPointMake(xVal, yVal)


↓CGSizeMake(10, 10)


↓CGSizeMake(aWidth, aHeight)


↓CGRectMake(0, 0, 10, 10)


↓CGRectMake(xVal, yVal, width, height)


↓CGVectorMake(10, 10)


↓CGVectorMake(deltaX, deltaY)


↓NSMakePoint(10, 10)


↓NSMakePoint(xVal, yVal)


↓NSMakeSize(10, 10)


↓NSMakeSize(aWidth, aHeight)


↓NSMakeRect(0, 0, 10, 10)


↓NSMakeRect(xVal, yVal, width, height)


↓NSMakeRange(10, 1)


↓NSMakeRange(loc, len)


↓UIEdgeInsetsMake(0, 0, 10, 10)


↓UIEdgeInsetsMake(top, left, bottom, right)


↓NSEdgeInsetsMake(0, 0, 10, 10)


↓NSEdgeInsetsMake(top, left, bottom, right)

```

## Further Reading

* [SwiftLint - Legacy Constructor](https://github.com/realm/SwiftLint/blob/master/Rules.md#legacy-constructor)