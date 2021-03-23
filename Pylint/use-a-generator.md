Pattern: Use of comprehension in `any`/`all`

Issue: -

## Description

Comprehension inside of `any` or `all` is unnecessary. A generator would be sufficient and faster.

Example of **incorrect** code:

```python
any([0 for x in list(range(10))]) # [use-a-generator]
```

Example of **correct** code:

```python
any(0 for x in list(range(10)))
```