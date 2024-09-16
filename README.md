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
