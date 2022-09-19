# Merge two sorted arrays into one

[Question](https://www.codewars.com/kata/5899642f6e1b25935d000161/javascript)

## Solutions

```javascript
function mergeArrays(arr1, arr2) {
  return Array.from(new Set([...arr1, ...arr2])).sort((a, b) => a - b);
}
```

## Pickups

**`Set()`**

可以接受 iterable 物件為傳入值，而且會去除 iterable 值內重覆的元素。

[Set() constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/Set)

**`Array.from()`**

可接受 iterable 為傳入值，再回傳新的陣列。

[Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)

**JavaScript 原生的 iterable 物件**

- String
- Array
- TypedArray
- Map / WeakMap
- Set / WeakSet
- Intl.Segments

[Iteration protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
