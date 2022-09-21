# Polish alphabet

[Question](https://www.codewars.com/kata/57ab2d6072292dbf7c000039/javascript)

## Solutions

```javascript
function correctPolishLetters(string) {
  const mappings = {
    ą: "a",
    ć: "c",
    ę: "e",
    ł: "l",
    ń: "n",
    ó: "o",
    ś: "s",
    ź: "z",
    ż: "z",
  };

  return string
    .split("")
    .map((char) => mappings[char] || char)
    .join("");
}
```

## Takeaways

JavaScript 字串具有 immutable 特性：

```javascript
const str = "abcde";

console.log(str[0]); // "a"

str[0] = "x";

console.log(str); // "abcde"
```

[Are JavaScript strings immutable? Do I need a "string builder" in JavaScript?](https://stackoverflow.com/questions/51185/are-javascript-strings-immutable-do-i-need-a-string-builder-in-javascript)

[What does immutable mean?](https://stackoverflow.com/questions/3200211/what-does-immutable-mean)
