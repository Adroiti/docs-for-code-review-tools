Pattern: Var func null

Issue: -

## Description

Passing NULL after the last typed argument to a variadic function leads to undefined behaviour.
The C99 standard, in section 7.15.1.1, states that if the type used by `va_ar`g()`` is not compatible with the type of the actual next argument (as promoted according to the default argument promotions), the behavior is undefined.
The value of the NULL macro is an implementation-defined null pointer constant (7.17), which can be any integer constant expression with the value 0, or such an expression casted to (void*) (6.3.2.3). This includes values like 0, 0L, or even 0LL.
In practice on common architectures, this will cause real crashes if sizeof(int) != sizeof(void*), and NULL is defined to 0 or any other null pointer constant that promotes to int.
To reproduce you might be able to use this little code example on 64bit platforms. If the output includes "ERROR", the sentinel had only 4 out of 8 bytes initialized to zero and was not detected as the final argument to stop argument processing via `va_ar`g()``. Changing the 0 to (void*)0 or 0L will make the "ERROR" output go away.
#include <stdarg.h>
#include <stdio.h>

void f(char *s, ...) {
    va_list ap;
    va_start(ap,s);
    for (;;) {
        char *p = va_arg(ap,char*);
        printf("%018p, %s\n", p, (long)p & 255 ? p : "");
        if(!p) break;
    }
    va_end(ap);
}

void `g()` {
    char *s2 = "x";
    char *s3 = "ERROR";

    // changing 0 to 0L for the 7th argument (which is intended to act as sentinel) makes the error go away on x86_64
    f("first", s2, s2, s2, s2, s2, 0, s3, (char*)0);
}

void `h()` {
    int i;
    volatile unsigned char a[1000];
    for (i = 0; i<sizeof(a); i++)
        a[i] = -1;
}

int `main()` {
    `h()`;
    `g()`;
    return 0;
}

## Further Reading

* [Common Weakness Enumeration (CWE) - 475](https://cwe.mitre.org/data/definitions/475.html)