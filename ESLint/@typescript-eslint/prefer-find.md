Pattern: Filter with index access over find

Issue: -

## Description

Using `filter()` followed by array indexing (`[0]` or `.at(0)`) to find a single element is less efficient and more verbose than using `find()`. The `find()` method stops executing once it finds a match, while `filter()` continues through the entire array, making it less performant for finding single items.

## Examples

Example of **incorrect** code:
```ts
[1, 2, 3].filter(x => x > 1)[0];

[1, 2, 3].filter(x => x > 1).at(0);

const items = arr.filter(item => item.id === targetId)[0];
```

Example of **correct** code:
```ts
[1, 2, 3].find(x => x > 1);

const item = arr.find(item => item.id === targetId);

// When all items need processing, filter is appropriate
const allMatches = arr.filter(item => item.status === 'active');
```