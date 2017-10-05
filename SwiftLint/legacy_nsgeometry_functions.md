Pattern: Use of legacy `NSGeometry` function

Issue: -

## Description

Struct extension properties and methods are preferred over legacy functions.

Examples of **correct** code:
```swift
rect.width


rect.height


rect.minX


rect.midX


rect.maxX


rect.minY


rect.midY


rect.maxY


rect.isEmpty


rect.integral


rect.insetBy(dx: 5.0, dy: -7.0)


rect.offsetBy(dx: 5.0, dy: -7.0)


rect1.union(rect2)


rect1.intersect(rect2)


rect1.contains(rect2)


rect.contains(point)


rect1.intersects(rect2)

```
Examples of **incorrect** code:
```swift

↓NSWidth(rect)


↓NSHeight(rect)


↓NSMinX(rect)


↓NSMidX(rect)


↓NSMaxX(rect)


↓NSMinY(rect)


↓NSMidY(rect)


↓NSMaxY(rect)


↓NSEqualRects(rect1, rect2)


↓NSEqualSizes(size1, size2)


↓NSEqualPoints(point1, point2)


↓NSEdgeInsetsEqual(insets2, insets2)


↓NSIsEmptyRect(rect)


↓NSIntegralRect(rect)


↓NSInsetRect(rect, 10, 5)


↓NSOffsetRect(rect, -2, 8.3)


↓NSUnionRect(rect1, rect2)


↓NSIntersectionRect(rect1, rect2)


↓NSContainsRect(rect1, rect2)


↓NSPointInRect(rect, point)


↓NSIntersectsRect(rect1, rect2)

```

## Further Reading

* [SwiftLint - Legacy NSGeometry Functions](https://github.com/realm/SwiftLint/blob/master/Rules.md#legacy-nsgeometry-functions)