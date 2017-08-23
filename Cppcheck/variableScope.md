Pattern: Variable scope

Issue: -

## Description

The scope of the variable `varname` can be reduced. Warning: Be careful when fixing this message, especially when there are inner loops. Here is an example where cppcheck will write that the scope for `i` can be reduced:
void f(int x)
{
    int i = 0;
    if (x) {
        // it`s safe to move `int i = 0;` here
        for (int n = 0; n < 10; ++n) {
            // it is possible but not safe to move `int i = 0;` here
            do_something(&i);
        }
    }
}
When you see this message it is always safe to reduce the variable scope 1 level.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)