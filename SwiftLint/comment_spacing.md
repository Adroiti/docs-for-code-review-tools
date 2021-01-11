Pattern: Malformed comment spacing

Issue: -

## Description

Prefer at least one space after slashes for comments.

Examples of **correct** code:

```swift
// This is a comment

/// Triple slash comment

// Multiline double-slash
// comment

/// Multiline triple-slash
/// comment

/// Multiline triple-slash
///   - This is indented

// - MARK: Mark comment

/* Asterisk comment */

/*
    Multiline asterisk comment
*/
   }
}
```

Examples of **incorrect** code:

```swift
//↓Something

//↓MARK

//↓👨‍👨‍👦‍👦Something

func a() {
    //↓This needs refactoring
    print("Something")
}
//↓We should improve above function

///↓This is a comment

/// Multiline triple-slash
///↓This line is incorrect, though

//↓- MARK: Mark comment

```

## Further Reading

* [SwiftLint - Test case accessibility](https://realm.github.io/SwiftLint/comment_spacing.html)