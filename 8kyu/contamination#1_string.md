# Contamination #1 -String-

[Question](https://www.codewars.com/kata/596fba44963025c878000039/javascript)

## Solutions

```javascript
function contamination(text, char) {
  return text.split("").fill(char).join("");
}

/////////////////////////////////////////////////

function contamination(text, char) {
  return char.repeat(text.length);
}

/////////////////////////////////////////////////

// Regex /./ 會符合任意單一字元
function contamination(text, char) {
  return text.replace(/./g, char);
}
```

## Takeaways

**`Array.fill()`**

會**修改**原有陣列，內部元素皆取代為傳入值，會回傳出**原有陣列**：

```javascript
const a = [1, 1, 1];
const b = a.fill(0);

console.log({ a, b }); // 皆為 [0, 0, 0]
```

可指定取代範圍：

```javascript
// Array.fill(VALUE, START_ID)
const a = [1, 1, 1];
a.fill("a", 1);

console.log({ a }); // [1, 'a', 'a']

// Array.fill(VALUE, START_ID, END_ID)
const a = [1, 1, 1];
a.fill("a", 0, 1);

console.log({ a }); // ['a', 1, 1]
```
