Pattern: Missing use of `.isButton`/`.isLink`

Issue: -

## Description

All views with tap gestures added should include the `.isButton` accessibility trait. If a tap opens an external link the `.isLink` trait should be used instead.

Examples of **correct** code:

```swift
struct MyView: View {
    var body: some View {
        Button {
            print("tapped")
        } label: {
            Text("Learn more")
        }
    }
}

struct MyView: View {
    var body: some View {
        Link("Open link", destination: myUrl)
    }
}
struct MyView: View {
    var body: some View {
        Text("Learn more")
            .onTapGesture {
                print("tapped - open URL")
            }
            .accessibility(addTraits: .isLink)
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .accessibilityAddTraits(.isButton)
            .onTapGesture {
                print("tapped")
            }
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .accessibility(addTraits: [.isButton, .isHeader])
            .onTapGesture {
                print("tapped")
            }
    }
}
struct MyView: View {
    var body: some View {
        Text("Learn more")
            .onTapGesture {
                print("tapped - open URL")
            }
            .accessibilityAddTraits([.isHeader, .isLink])
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .onTapGesture(count: 1) {
                print("tapped")
            }
            .accessibility(addTraits: .isButton)
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .onTapGesture(count: 1, perform: {
                print("tapped")
            })
            .accessibility(addTraits: .isButton)
    }
}
struct MyView: View {
    var body: some View {
        Text("Learn more")
            // This rule does not include tap gestures with multiple taps for now.
            // Custom gestures like this are also not very accessible, but require
            // alternative ways to accomplish the same task with assistive tech.
            .onTapGesture(count: 2) {
                print("double-tapped")
            }
    }
}
struct MyView: View {
    var body: some View {
        Label("Learn more", systemImage: "info.circle")
            .onTapGesture(count: 1) {
                print("tapped")
            }
            .accessibility(addTraits: .isButton)
    }
}

struct MyView: View {
    var body: some View {
        HStack {
            Image(systemName: "info.circle")
            Text("Learn more")
        }
        .onTapGesture {
            print("tapped")
        }
        // This modifier is not strictly required — each subview will inherit the button trait.
        // That said, grouping a tappable stack into a single element is a good way to reduce
        // the number of swipes required for a VoiceOver user to navigate the page.
        .accessibilityElement(children: .combine)
        .accessibility(addTraits: .isButton)
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .gesture(TapGesture().onEnded {
                print("tapped")
            })
            .accessibilityAddTraits(.isButton)
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .simultaneousGesture(TapGesture(count: 1).onEnded {
                print("tapped - open URL")
            })
            .accessibilityAddTraits(.isLink)
    }
}
struct MyView: View {
    var body: some View {
        Text("Learn more")
            .highPriorityGesture(TapGesture().onEnded {
                print("tapped")
            })
            .accessibility(addTraits: [.isButton])
    }
}

struct MyView: View {
    var body: some View {
        Text("Learn more")
            .gesture(TapGesture(count: 2).onEnded {
                print("tapped")
            })
    }
}
```

Examples of **incorrect** code:

```swift
struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .onTapGesture {
                print("tapped")
            }
    }
}

struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .accessibility(addTraits: .isHeader)
            .onTapGesture {
                print("tapped")
            }
    }
}
struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .onTapGesture(count: 1) {
                print("tapped")
            }
    }
}

struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .onTapGesture(count: 1, perform: {
                print("tapped")
            })
    }
}

struct MyView: View {
    var body: some View {
        ↓Label("Learn more", systemImage: "info.circle")
            .onTapGesture(count: 1) {
                print("tapped")
            }
    }
}

struct MyView: View {
    var body: some View {
        ↓HStack {
            Image(systemName: "info.circle")
            Text("Learn more")
        }
        .onTapGesture {
            print("tapped")
        }
    }
}

struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .gesture(TapGesture().onEnded {
                print("tapped")
            })
    }
}

struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .simultaneousGesture(TapGesture(count: 1).onEnded {
                print("tapped")
            })
    }
}

struct MyView: View {
    var body: some View {
        ↓Text("Learn more")
            .highPriorityGesture(TapGesture().onEnded {
                print("tapped")
            })
    }
}
```

## Further Reading

* [SwiftLint - Accessibility Trait for Button](https://realm.github.io/SwiftLint/accessibility_trait_for_button.html)