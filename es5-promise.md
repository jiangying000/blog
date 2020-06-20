# es5 promise polyfill

Promise 是 es6 用于解决回调地狱的方案，通过用es5写一个 promise 的polyfill，可以帮助我们深入理解异步的概念和JavaScript这门语言。

我们在实现中使用ecmascript标准中的术语，如executor，resolver，fulfilled，rejected

```js
var PENDING = 'pending'
var RESOLVED = 'resolved'
var REJECTED = 'rejected'
new Promise(function() {
  this.status = PENDING
  function resolve() {
  }
  function reject() {

  }
  try {
    executor(resolve, reject)
  } catch(e) {
    reject(e)
  }
})
```

```js
function MyPromise(executor) {

}

MyPromise.prototype.then = function then() {

}
```
