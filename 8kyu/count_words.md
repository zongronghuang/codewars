# Count words

[Question](https://www.codewars.com/kata/570cc83df616a85944001315/javascript)

## Solutions

```javascript
const countWords = (str) => str.split(/\s+/).filter((x) => x).length;
```

## Takeaways

**`String.split()`**

裡面的分隔點可以是字串或正規表達式：

```javascript
const str = "a b c d";

const arr1 = str.split(" "); // ['a', 'b', 'c', 'd']

const arr2 = str.split(/\s/g); // ['a', 'b', 'c', 'd']
```
