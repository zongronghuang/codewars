# Arguments to Binary addition

[Question](https://www.codewars.com/kata/57642a90dee2da8dd3000161)

## Solutions

```javascript
function arr2bin(arr) {
  return arr
    .reduce((sum, cur) => (typeof cur === "number" ? sum + cur : sum), 0)
    .toString(2);
}
```

## Takeaways

**`.toString(radix)`**

可將十進位數字轉換成其他進位制的數字字串。`radix` 範圍為 2 到 36 之間的整數。預設為 10 進位。

```javascript
const num = 100;

const numWithRadix2 = num.toString(2); // "1100100"
const numWithRadix8 = num.toString(8); // "144"
const numWithRadix16 = num.toString(16); // "64"
```
