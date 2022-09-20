# Is there a vowel in there?

[Question](https://www.codewars.com/kata/57cff961eca260b71900008f/javascript)

## Solutions

```javascript
function isVow(a) {
  const vowelCharCodes = ["a", "e", "i", "o", "u"].map((vowel) =>
    vowel.charCodeAt()
  );
  return a.map((num) =>
    vowelCharCodes.includes(num) ? String.fromCharCode(num) : num
  );
}
```

## Takeaways

**`String.charCodeAt(id)`**

會將指定位置的字元轉換成代表 UTF-16 編碼位置的整數 (0 到 65535)。不指定字元位置的話，預設 `id = 0`

```javascript
const string = "你好";

string.charCodeAt(); // 你 20320
string.charCodeAt(1); // 好 22909
```

[String.prototype.charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)

**`String.fromCharCode(UTF_16_value)`**

會將整數 (UTF-16 編碼位置範圍內；0 到 65535) 轉換為對應字元。可以一次傳入多個整數。

```javascript
const utf16Values = [20320, 22909];
String.fromCharCode(...utf16Values); // 你好
```

[String.fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)
