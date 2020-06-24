# Test performance of array vs push

- For large array allocation, the performance is different between we first allocation the array of target size and push every time.

- The actual gap is 10 million for array size to differ.

```js
for (const n of [4, 5, 6, 7, 8]) {
  console.log('-----------------')
  test(10 ** n)
  console.log('-----------------')
}
function test(n) {
  console.log('testing: size is ' + n)
  console.time();
  const a = Array(n);
  for (let i = 0; i < n; i++) {
    a[i] = i;
  }
  console.timeEnd();
  console.time();
  const b = [];
  for (let i = 0; i < n; i++) {
    b.push(i);
  }
  console.timeEnd();
  console.time();
  const c = Array(n);
  for (let i = 0; i < n; i++) {
    c[i] = i;
  }
  console.timeEnd();
}
```
