# Game hit the target

[Question](https://www.codewars.com/kata/5ffc226ce1666a002bf023d2/javascript)

## Solutions

```javascript
const solution = (mtrx) => {
  const arr =
    mtrx.filter((el) => el.includes(">") && el.includes("x"))[0] || [];
  return arr.indexOf(">") < arr.indexOf("x");
};

///////////////////////////////////

const solution = (mtrx) => {
  const targetArray = mtrx.find(
    (array) => array.includes("x") && array.includes(">")
  );

  if (!targetArray || targetArray.indexOf("x") < targetArray.indexOf(">")) {
    return false;
  }
  return true;
};
```

## Takeaways

**`Array.filter()` vs `Array.find()`**

```javascript
const arr = [0, 1, 2, 3, 4, 5];

// callback 皆為判斷式
// filter 回傳 shallow copy 陣列，內含符合判斷式的元素
// find 回傳第一個符合的元素 (如果元素是物件，會有 copy by reference 問題)
const positiveIntegers1 = arr.filter((number) => number > 0); // [1, 2, 3, 4, 5]
const positiveIntegers2 = arr.find((number) => number > 0); // 1

// 空值
// filter 回傳空陣列
// find 回傳 undefined
const negativeIntegers1 = arr.filter((number) => number < 0); // []
const negativeIntegers2 = arr.find((number) => number < 0); // undefined
```

**`Array.find()` vs `Array.findIndex()` vs `Array.findLast()` vs `Array.findLastIndex()`**

-find 開頭的方法都需要一個判斷式 callback。

- `find`：回傳第一個符合的元素；找不到元素則回傳 `undefined`
- `findLast`：回傳最後一個符合的元素；找不到元素則回傳 `undefined`
- `findIndex`：回傳第一個符合的元素的 id；找不到元素則回傳 `-1`
- `findLastIndex`：回傳最後一個符合的元素的 id；找不到元素則回傳 `-1`
