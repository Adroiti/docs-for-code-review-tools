Pattern: Synchronized on boxed primitive

Issue: -

## Description

The code synchronizes on a boxed primitive constant, such as an Integer. Since Integer objects can be cached and shared, this code could be synchronizing on the same object as other, unrelated code, leading to unresponsiveness and possible deadlock.

Example of violations:

``` groovy
class SomeClass {
    Byte byte1 = 100
    Short short1 = 1
    Double double1 = 1
    Integer integer1 = 1
    Long long1 = 1
    Float float1 = 1
    Character char1 = 1

    byte byte2 = getValue()
    short short2 = getValue()
    double double2 = getValue()
    int integer2 = getValue()
    long long2 = getValue()
    float float2 = getValue()
    char char2 = getValue()

    def byte3 = new Byte((byte)100)
    def short3 = new Short((short)1)
    def double3 = new Double((double)1)
    def integer3 = new Integer(1)
    def long3 = new Long(1)
    def float3 = new Float(1)
    def char3 = new Character((char)'1')

    def byte4 = 1 as byte
    def short4 = 1 as short
    def double4 = 1 as double
    def integer4 = 1 as int
    def long4 = 1 as long
    def float4 = 1 as float
    def char4 = 1 as char

    def byte5 = 1 as Byte
    def short5 = 1 as Short
    def double5 = 1 as Double
    def integer5 = 1 as Integer
    def long5 = 1 as Long
    def float5 = 1 as Float
    def char5 = 1 as Character

    def byte6 = (byte)1
    def short6 = (short)1
    def double6 = (double)1
    def integer6 = (int)1
    def long6 = (long)1
    def float6 = (float)1
    def char6 = (char)1

    def method() {
        // all of these synchronization blocks produce violations
        synchronized(byte1) {}
        synchronized(short1) {}
        synchronized(double1) {}
        synchronized(integer1) {}
        synchronized(long1) {}
        synchronized(float1) {}
        synchronized(char1) {}

        synchronized(byte2) {}
        synchronized(short2) {}
        synchronized(double2) {}
        synchronized(integer2) {}
        synchronized(long2) {}
        synchronized(float2) {}
        synchronized(char2) {}

        synchronized(byte3) {}
        synchronized(short3) {}
        synchronized(double3) {}
        synchronized(integer3) {}
        synchronized(long3) {}
        synchronized(float3) {}
        synchronized(char3) {}

        synchronized(byte4) {}
        synchronized(short4) {}
        synchronized(double4) {}
        synchronized(integer4) {}
        synchronized(long4) {}
        synchronized(float4) {}
        synchronized(char4) {}

        synchronized(byte5) {}
        synchronized(short5) {}
        synchronized(double5) {}
        synchronized(integer5) {}
        synchronized(long5) {}
        synchronized(float5) {}
        synchronized(char5) {}

        synchronized(byte6) {}
        synchronized(short6) {}
        synchronized(double6) {}
        synchronized(integer6) {}
        synchronized(long6) {}
        synchronized(float6) {}
        synchronized(char6) {}
    }
}
```

And here is an in-depth example of how it works within inner classes and such:

``` groovy
class SomeClass {

    final String lock = false

    def method() {
        // violation
        synchronized(lock) { }
    }
}

class SomeClass {

    final String lock = false

    class SomeInnerClass {
        def method() {
            // violation
            synchronized(lock) { }
        }
    }
}

class SomeClass {
    // implicit typing
    final def lock = true

    def method() {
        // violation
        synchronized(lock) { }
    }
}

class SomeClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    def method() {
        return new Runnable() {
            final def lock = false // shadows parent from inner class
            public void run() {
                // violation
                synchronized(stringLock) { }
            }
        }
    }
}

class SomeClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    class SomeInnerClass {

        final def lock = true // shadows parent from inner class
        def method() {
            // violation
            synchronized(stringLock) { }
        }
    }
}
```

## Further Reading

* [CodeNarc - SynchronizedOnBoxedPrimitive](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#SynchronizedOnBoxedPrimitive)