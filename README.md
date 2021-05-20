# js-arguments-test

This is a micro benchmark test for comparing the performance and memory allocation among the following three JavaScript function arguments styles.

```javascript
function normalOp(a, b) {
  return other(a, b);
}

function leakyArguments() {
  return other.apply(this, arguments);
}

const spreadOp = (...args) => {
  return other.apply(this, args);
};
```

[Online Demo](https://rawcdn.githack.com/takahirox/js-arguments-test/v1.0.0/index.html)
