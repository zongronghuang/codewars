# Gravity Flip

[Question](https://www.codewars.com/kata/5f70c883e10f9e0001c89673/javascript)

## Solutions

```javascript
const flip = (d, a) =>
  d === "R" ? a.sort((x, y) => x - y) : a.sort((x, y) => y - x);
```

## Pickups

`Array.sort()` 會直接修改原有的陣列，不會回傳新陣列。

**不帶 compare function**
用 Unicode 順序 (字典順序) 排序。不管陣列元素是什麼型別，一律先轉成字串再比較。

從第一個字元開始比較；如果前面的字元都一樣，再比較下一個字元：

```
[1, 11111, 20, 22, 3]

["abcde","b","cccccc","cddd"]
```

**帶 compare function**

比較元素的大小來排序 (數學意義)，而非用字典順序排序。有精簡和比較複雜、更有彈性的寫法。

精簡寫法：

```javascript
const incrementalSort = (a, b) => a - b
const decrementalSort = (a, b) => b - a

[...].sort(incrementalSort)
```

複雜寫法：

```javascript
const incrementalSort = (a, b) => {
  const diff = a - b

  if (diff > 0) {return 1}     // 符合條件，a 往後放 (a 的 id + 1)
  if (diff === 0) {return 0}   // 符合條件，a 不變
  if (diff < 0) {return -1 }   // 符合條件，a 往前放 (a 的 id - 1)
}

const decrementalSort = (a, b) => {
  const diff = a - b

  if (diff > 0) {return -1}     // 符合條件，a 往前放 (a 的 id - 1)
  if (diff === 0) {return 0}    // 符合條件，a 不變
  if (diff < 0) {return 1 }     // 符合條件，a 往後放 (a 的 id + 1)
}

[...].sort(incrementalSort)
```

> :bangbang: 要注意的是，每個瀏覽器底層實作 `Array.sort()` 的方式不同。同樣的語句在不同瀏覽器上可能有不同結果。
