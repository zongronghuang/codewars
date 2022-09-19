# Multiple of index

[Question](https://www.codewars.com/kata/5a34b80155519e1a00000009)

## Solutions

```javascript
function multipleOfIndex(array) {
  return array.filter((num, i) => num % i === 0);
}
```

## Pickups

**`Array.filter()`**

裡面會放入一個篩選元素用的 callback 函式。然而，callback 回傳的必須是篩選條件，而非符合條件的元素：

```javascript
const arr = [1, 2, 3, 4];

arr.filter((x) => x % 2 === 0); // [2, 4]

arr.filter((x) => {
  return x % 2 === 0;
}); // [2, 4]
```

[Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
