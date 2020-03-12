Pattern: Malformed file header

Issue: -

## Description

Header comments should be consistent with project patterns.

Examples of **correct** code:
```swift
let foo = "Copyright"


let foo = 2 // Copyright


let foo = 2
 // Copyright

```
Examples of **incorrect** code:
```swift

// ↓Copyright


//
// ↓Copyright


//
//  FileHeaderRule.swift
//  SwiftLint
//
//  Created by Marcelo Fabri on 27/11/16.
//  ↓Copyright © 2016 Realm. All rights reserved.
//

```

## Further Reading

* [SwiftLint - File Header](https://realm.github.io/SwiftLint/file_header.html)