# Last survivor

[Question](https://www.codewars.com/kata/609eee71109f860006c377d1/javascript)

## Solutions

```javascript
function lastSurvivor(letters, coords) {
  return coords.reduce(
    (letters, targetId) =>
      letters.substring(0, targetId) + letters.substring(targetId + 1),
    letters
  );
}

/////////////////////////////////////////

function lastSurvivor(string, indices) {
  const arr = [...string];
  for (const i of indices) arr.splice(i, 1);
  return arr[0];
}
```

## Takeaways

**`Array.splice()` vs `Array.slice()`**

`Array.splice(元素 id, 刪除數量, 新值1, 新值2, ...)` 是疊接／接合陣列內的元素，可以指定陣列內某個 id 元素並用新值取代。

這個方法會修改原有陣列，回傳被刪除元素組成的陣列。

```javascript
const arr = [0, 1, 2, 3, 4];

const deletedElements = arr.splice(1, 2, "x");

console.log(arr); // [0, 'x', 3, 4]
console.log(deletedElements); // [1, 2]
```

`Array.slice(startId, endId)` 回傳開頭 id 和結尾 id (不包含) 之間元素組成的陣列，不修改原有陣列。id 可為負值。

```javascript
const arr = [0, 1, 2, 3, 4, 5];

const smallArr1 = arr.slice(4); // [4, 5]
const smallArr2 = arr.slice(1, 4); // [1, 2, 3]

// id 可以為負值
// 開頭 id 可以大於結尾 id，但結尾 id 要是負值
const smallArr3 = arr.slice(-2); // [4, 5]
const smallArr4 = arr.slice(3, -1); // [3，4]
const smallArr5 = arr.slice(3, 0); // []
```

**`String.slice()` vs `String.substring()`**

`String.slice(startId, endId)` 回傳開頭 id 和結尾 id (不包含) 之間的字串，不修改原有字串。id 可為負值。

建議使用 `String.slice()`：

- 行為比 `String.substring()` 規律許多。
- 和 `Array.slice()` 行為相當，容易記憶。

```javascript
const str = "012345";

const str1 = str.slice(3); // '345'
const str2 = str.slice(1, 4); // '123'

// id 可以為負值
// 開頭 id 可以大於結尾 id，但結尾 id 要是負值
const str3 = str.slice(-2); // '45'
const str4 = str.slice(3, -1); // '34'
const str5 = str.slice(3, 0); // ''
```

`String.substring(startId, endId)` 回傳開頭 id 和結尾 id (不包含) 之間的字串，不修改原有字串。

- id 僅可為正值。id 為負值時，校正為 `0`。
- 如果開頭 id 大於結尾 id，兩者會互換位置，達到開頭 id 小於結尾 id 的要求。

```javascript
const str = "012345";

const str1 = str.substring(3); // '345'
const str2 = str.substring(1, 4); // '123'

// 負值 id 校正為 0
// 開頭 id 大於結尾 id 時，兩者互換位置
const str3 = str.substring(-2); // '012345'
const str4 = str.substring(3, -1); // '012'
const str5 = str.substring(3, 0); // '012'
```

[What is the difference between String.slice and String.substring?](https://stackoverflow.com/questions/2243824/what-is-the-difference-between-string-slice-and-string-substring)
