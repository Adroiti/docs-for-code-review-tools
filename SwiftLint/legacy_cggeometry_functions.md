Pattern: Use of legacy `CGGeometry` function

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


rect.isNull


rect.isEmpty


rect.isInfinite


rect.standardized


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

↓CGRectGetWidth(rect)


↓CGRectGetHeight(rect)


↓CGRectGetMinX(rect)


↓CGRectGetMidX(rect)


↓CGRectGetMaxX(rect)


↓CGRectGetMinY(rect)


↓CGRectGetMidY(rect)


↓CGRectGetMaxY(rect)


↓CGRectIsNull(rect)


↓CGRectIsEmpty(rect)


↓CGRectIsInfinite(rect)


↓CGRectStandardize(rect)


↓CGRectIntegral(rect)


↓CGRectInset(rect, 10, 5)


↓CGRectOffset(rect, -2, 8.3)


↓CGRectUnion(rect1, rect2)


↓CGRectIntersection(rect1, rect2)


↓CGRectContainsRect(rect1, rect2)


↓CGRectContainsPoint(rect, point)


↓CGRectIntersectsRect(rect1, rect2)

```

## Further Reading

* [SwiftLint - Legacy CGGeometry Functions](https://github.com/realm/SwiftLint/blob/master/Rules.md#legacy-cggeometry-functions)