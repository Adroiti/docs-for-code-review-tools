Pattern: Wrong import order

Issue: -

## Description

Consistent import ordering improves code readability and reduces unrelated changes in patches.

Examples of **correct** code:
```swift
import AAA
import BBB
import CCC
import DDD


import Alamofire
import API


import labc
import Ldef

```
Examples of **incorrect** code:
```swift

import AAA
import ZZZ
import ↓BBB
import CCC

```

## Further Reading

* [SwiftLint - Sorted Imports](https://realm.github.io/SwiftLint/sorted_imports.html)