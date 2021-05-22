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

We added some test cases

```javascript
function indexedArguments() {
  return other(arguments[0], arguments[1]);
}

function fastArgLength(a, b) {
  if (arguments.length > 0) {
    return other(a, b);
  }
  return 0;
}

function slowArgLength(a, b) {
  if (arguments.length > 2) {
    return other(a, b);
  }
  return 0;
}
```

[Online Demo](https://rawcdn.githack.com/takahirox/js-arguments-test/v1.0.1/index.html)
