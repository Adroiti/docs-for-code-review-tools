Pattern: Use of postfix increment/decrement

Issue: -

## Description

Use prefix form (`++i`) of the increment and decrement operators with iterators and other template objects. For example following function:


```cpp
void increment_counter(int* count) {
*count++;
}
```

is invalid, because it effectively does count++, moving pointer, and should be replaced with `++*count, (*count)++` or `*count += 1`.

## Further Reading

* [Google C++ Style Guide - Preincrement and Predecrement](https://google.github.io/styleguide/cppguide.html#Preincrement_and_Predecrement)