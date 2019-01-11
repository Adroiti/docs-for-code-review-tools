Pattern: Comparing two identical operands

Issue: -

## Description

Comparing two identical operands is likely a mistake.

Examples of **correct** code:
```swift
1 == 2


foo == bar


prefixedFoo == foo


foo.aProperty == foo.anotherProperty


self.aProperty == self.anotherProperty


"1 == 1"


self.aProperty == aProperty


lhs.aProperty == rhs.aProperty


lhs.identifier == rhs.identifier


i == index


$0 == 0


keyValues?.count ?? 0  == 0


1 != 2


foo != bar


prefixedFoo != foo


foo.aProperty != foo.anotherProperty


self.aProperty != self.anotherProperty


"1 != 1"


self.aProperty != aProperty


lhs.aProperty != rhs.aProperty


lhs.identifier != rhs.identifier


i != index


$0 != 0


keyValues?.count ?? 0  != 0


1 === 2


foo === bar


prefixedFoo === foo


foo.aProperty === foo.anotherProperty


self.aProperty === self.anotherProperty


"1 === 1"


self.aProperty === aProperty


lhs.aProperty === rhs.aProperty


lhs.identifier === rhs.identifier


i === index


$0 === 0


keyValues?.count ?? 0  === 0


1 !== 2


foo !== bar


prefixedFoo !== foo


foo.aProperty !== foo.anotherProperty


self.aProperty !== self.anotherProperty


"1 !== 1"


self.aProperty !== aProperty


lhs.aProperty !== rhs.aProperty


lhs.identifier !== rhs.identifier


i !== index


$0 !== 0


keyValues?.count ?? 0  !== 0


1 > 2


foo > bar


prefixedFoo > foo


foo.aProperty > foo.anotherProperty


self.aProperty > self.anotherProperty


"1 > 1"


self.aProperty > aProperty


lhs.aProperty > rhs.aProperty


lhs.identifier > rhs.identifier


i > index


$0 > 0


keyValues?.count ?? 0  > 0


1 >= 2


foo >= bar


prefixedFoo >= foo


foo.aProperty >= foo.anotherProperty


self.aProperty >= self.anotherProperty


"1 >= 1"


self.aProperty >= aProperty


lhs.aProperty >= rhs.aProperty


lhs.identifier >= rhs.identifier


i >= index


$0 >= 0


keyValues?.count ?? 0  >= 0


1 < 2


foo < bar


prefixedFoo < foo


foo.aProperty < foo.anotherProperty


self.aProperty < self.anotherProperty


"1 < 1"


self.aProperty < aProperty


lhs.aProperty < rhs.aProperty


lhs.identifier < rhs.identifier


i < index


$0 < 0


keyValues?.count ?? 0  < 0


1 <= 2


foo <= bar


prefixedFoo <= foo


foo.aProperty <= foo.anotherProperty


self.aProperty <= self.anotherProperty


"1 <= 1"


self.aProperty <= aProperty


lhs.aProperty <= rhs.aProperty


lhs.identifier <= rhs.identifier


i <= index


$0 <= 0


keyValues?.count ?? 0  <= 0


func evaluate(_ mode: CommandMode) -> Result<AutoCorrectOptions, CommandantError<CommandantError<()>>>

```
Examples of **incorrect** code:
```swift

↓1 == 1


↓foo == foo


↓foo.aProperty == foo.aProperty


↓self.aProperty == self.aProperty


↓$0 == $0


↓1 != 1


↓foo != foo


↓foo.aProperty != foo.aProperty


↓self.aProperty != self.aProperty


↓$0 != $0


↓1 === 1


↓foo === foo


↓foo.aProperty === foo.aProperty


↓self.aProperty === self.aProperty


↓$0 === $0


↓1 !== 1


↓foo !== foo


↓foo.aProperty !== foo.aProperty


↓self.aProperty !== self.aProperty


↓$0 !== $0


↓1 > 1


↓foo > foo


↓foo.aProperty > foo.aProperty


↓self.aProperty > self.aProperty


↓$0 > $0


↓1 >= 1


↓foo >= foo


↓foo.aProperty >= foo.aProperty


↓self.aProperty >= self.aProperty


↓$0 >= $0


↓1 < 1


↓foo < foo


↓foo.aProperty < foo.aProperty


↓self.aProperty < self.aProperty


↓$0 < $0


↓1 <= 1


↓foo <= foo


↓foo.aProperty <= foo.aProperty


↓self.aProperty <= self.aProperty


↓$0 <= $0

```

## Further Reading

* [SwiftLint - Identical Operands](https://github.com/realm/SwiftLint/blob/master/Rules.md#identical-operands)