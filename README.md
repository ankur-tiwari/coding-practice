# String Expansion Script

This script takes a specially formatted string and expands it based on the numbers following each character. For example, given the input `"a4b11c7s3g1"`, the output will be `"aaaabbbbbbbbbbbbcccccccsssg"`.

## How It Works

The script processes the input string character by character. When it encounters a number, it accumulates it until it finds a non-numeric character. It then repeats the previous character based on the accumulated number.

## Code

```javascript
let str = 'a4b11c7s3g1';
let result = '';
let temp = '';

for (let i = 0; i < str.length; i++) {
  if (!isNaN(str[i])) {
    temp += str[i];
  } else {
    if (temp) {
      result += str[i - temp.length - 1].repeat(Number(temp));
      temp = '';
    }
  }
}

if (temp) {
  result += str[str.length - temp.length - 1].repeat(Number(temp));
}

console.log(result);
