Pattern: Multi-line function chain

Issue: -

## Description

Chained function calls should be either on the same line, or one per line.

Examples of **correct** code:
```swift
let evenSquaresSum = [20, 17, 35, 4].filter { $0 % 2 == 0 }.map { $0 * $0 }.reduce(0, +)


let evenSquaresSum = [20, 17, 35, 4]
    .filter { $0 % 2 == 0 }.map { $0 * $0 }.reduce(0, +)",


let chain = a
    .b(1, 2, 3)
    .c { blah in
        print(blah)
    }
    .d()


let chain = a.b(1, 2, 3)
    .c { blah in
        print(blah)
    }
    .d()


let chain = a.b(1, 2, 3)
    .c { blah in print(blah) }
    .d()


let chain = a.b(1, 2, 3)
    .c(.init(
        a: 1,
        b, 2,
        c, 3))
    .d()


self.viewModel.outputs.postContextualNotification
  .observeForUI()
  .observeValues {
    NotificationCenter.default.post(
      Notification(
        name: .ksr_showNotificationsDialog,
        userInfo: [UserInfoKeys.context: PushNotificationDialog.Context.pledge,
                   UserInfoKeys.viewController: self]
     )
    )
  }


let remainingIDs = Array(Set(self.currentIDs).subtracting(Set(response.ids)))


self.happeningNewsletterOn = self.updateCurrentUser
    .map { $0.newsletters.happening }.skipNil().skipRepeats()

```
Examples of **incorrect** code:
```swift

let evenSquaresSum = [20, 17, 35, 4]
    .filter { $0 % 2 == 0 }↓.map { $0 * $0 }
    .reduce(0, +)


let evenSquaresSum = a.b(1, 2, 3)
    .c { blah in
        print(blah)
    }↓.d()


let evenSquaresSum = a.b(1, 2, 3)
    .c(2, 3, 4)↓.d()


let evenSquaresSum = a.b(1, 2, 3)↓.c { blah in
        print(blah)
    }
    .d()


a.b {
//  ““
}↓.e()

```

## Further Reading

* [SwiftLint - Multiline Function Chains](https://realm.github.io/SwiftLint/multiline_function_chains.html)