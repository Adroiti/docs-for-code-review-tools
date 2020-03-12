Pattern: Duplicate import

Issue: -

## Description

Duplicate imports are unnecessary.

Examples of **correct** code:

```swift
import A
import B
import C


import A.B
import A.C


#if DEBUG
    @testable import KsApi
#else
    import KsApi
#endif


import A // module
import B // module
```

Examples of **incorrect** code:
```swift

import Foundation
import Dispatch
↓import Foundation


import Foundation
↓import Foundation.NSString

```

## Further Reading

* [SwiftLint - Duplicate Imports](https://realm.github.io/SwiftLint/duplicate_imports.html)