# js-arguments-test

This is a micro benchmark test for comparing the performance and memory allocation among the following four JavaScript function arguments styles.

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

function indexedArguments() {
  return other(arguments[0], arguments[1]);
}
```

We added an arguments.length check test.

```javascript
function argLength(a, b) {
  if (arguments.length < 3) {
    return other(a, b);
  }
  return 0;
}
```

[Online Demo](https://rawcdn.githack.com/takahirox/js-arguments-test/v1.0.2/index.html)
