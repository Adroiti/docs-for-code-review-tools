Pattern: Misaligned collection element

Issue: -

## Description

All elements in a collection literal should be vertically aligned.

Examples of **correct** code:
```swift
doThings(arg: [
    "foo": 1,
    "bar": 2,
    "fizz": 2,
    "buzz": 2
])


let abc = [
    "alpha": "a",
    "beta": "b",
    "gamma": "g",
    "delta": "d",
    "epsilon": "e"
]


let meals = [
                "breakfast": "oatmeal",
                "lunch": "sandwich",
                "dinner": "burger"
]


let coordinates = [
    CLLocationCoordinate2D(latitude: 0, longitude: 33),
    CLLocationCoordinate2D(latitude: 0, longitude: 66),
    CLLocationCoordinate2D(latitude: 0, longitude: 99)
]


var evenNumbers: Set<Int> = [
    2,
    4,
    6
]


let abc = [1, 2, 3, 4]


let abc = [
    1, 2, 3, 4
]


let abc = [
    "foo": "bar", "fizz": "buzz"
]

```
Examples of **incorrect** code:
```swift

doThings(arg: [
    "foo": 1,
    "bar": 2,
   ↓"fizz": 2,
   ↓"buzz": 2
])


let abc = [
    "alpha": "a",
     ↓"beta": "b",
    "gamma": "g",
    "delta": "d",
  ↓"epsilon": "e"
]


let meals = [
                "breakfast": "oatmeal",
                "lunch": "sandwich",
    ↓"dinner": "burger"
]


let coordinates = [
    CLLocationCoordinate2D(latitude: 0, longitude: 33),
        ↓CLLocationCoordinate2D(latitude: 0, longitude: 66),
    CLLocationCoordinate2D(latitude: 0, longitude: 99)
]


var evenNumbers: Set<Int> = [
    2,
  ↓4,
    6
]

```

## Further Reading

* [SwiftLint - Collection Element Alignment](https://github.com/realm/SwiftLint/blob/master/Rules.md#collection-element-alignment)