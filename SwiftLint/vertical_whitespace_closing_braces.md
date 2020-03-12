Pattern: Malformed whitespace before closing braces

Issue: -

## Description

Don't include vertical whitespace (empty line) before closing braces.

Examples of **correct** code:
```swift
        )
}
    }
}


    print("x is 5")
}


    print("x is 5")
}


    print("x is 5")
}


/*
    class X {

        let x = 5

    }
*/


[
1,
2,
3
]


[1, 2].map { $0 }.filter {


[1, 2].map { $0 }.filter { num in


class Name {
    run(5) { x in print(x) }
}


foo(
x: 5,
y:6
)

```
Examples of **incorrect** code:
```swift

        )
}
↓
    }
}


    print("x is 5")
↓

}


    print("x is 5")
↓
}


    print("x is 5")
↓    
}


[
1,
2,
3
↓
]


class Name {
    run(5) { x in print(x) }
↓
}


foo(
x: 5,
y:6
↓
)

```

## Further Reading

* [SwiftLint - Vertical Whitespace Closing Braces](https://realm.github.io/SwiftLint/vertical_whitespace_closing_braces.html)