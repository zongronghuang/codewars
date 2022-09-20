# Check same case

[Question](https://www.codewars.com/kata/5dd462a573ee6d0014ce715b)

## Solutions

```javascript
function sameCase(a, b) {
  const hasSpecialCharacter = -1;
  const sameCase = 1;
  const differentCases = 0;

  const getType = (char) => {
    if (char.match(/[a-z]/)) {
      return "lowercase";
    }
    if (char.match(/[A-Z]/)) {
      return "uppercase";
    }
    return "notLetter";
  };

  const types = [a, b].map((char) => getType(char));

  if (types.includes("notLetter")) {
    return hasSpecialCharacter;
  }
  if (types[0] === types[1]) {
    return sameCase;
  }
  return differentCases;
}
```

## Takeaways

**`String.match()`**

- 找到符合的字元，回傳陣列 (一個元素或多個元素)
- 找不到符合的字元，回傳 `null`

```javascript
const globalRegex = /[a-z]/g;
const firstMatchRegex = /[a-z]/;

const letters = "abc";
letters.match(globalRegex); // ['a', 'b', 'c']
letters.match(firstMatchRegex); // ['a'] 且陣列添加了其他屬性

const specialCharacters = "!?#";
specialCharacters.match(globalRegex); // null
specialCharacters.match(firstMatchRegex); // null
```

[String.prototype.match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match)
