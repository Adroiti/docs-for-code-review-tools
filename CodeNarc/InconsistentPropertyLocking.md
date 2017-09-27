Pattern: Inconsistent property locking

Issue: -

## Description

Class contains similarly-named `get` and `set` methods where one method of the pair is marked either `@WithReadLock` or `@WithWriteLock` and the other is not locked at all. This may result in incorrect behavior at runtime, as callers of the get and set methods will not necessarily lock correctly. The `get` and `set` methods should both be guarded by `@WithReadLock`/`@WithWriteLock` or neither should be guarded.

Example of violations:

``` groovy
class Person {
    String name
    Date birthday
    boolean deceased
    boolean parent

    @WithWriteLock setName(String name) {
        this.name = name
    }
    // violation, get method should be locked
    String getName() {
        name
    }

    // violation, set method should be locked
    void setBirthday(Date birthday) {
        this.birthday = birthday
    }

    @WithReadLock String getBirthday() {
        birthday
    }

    // violation, set method should be locked
    void setDeceased(boolean deceased) {
        this.deceased = deceased
    }

    @WithReadLock boolean isDeceased() {
        deceased
    }

    @WithWriteLock void setParent(boolean parent) {
        this.parent = parent
    }

    // violation, get method should be locked
    boolean isParent() {
        parent
    }
}
```

## Further Reading

* [CodeNarc - InconsistentPropertyLocking](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#InconsistentPropertyLocking)