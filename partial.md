## partial

#### Description

Partial application refers to the process of taking a function and returning a new function until all parameters to that function have been passed. The function that is partially applied, eventually resolves with a value once all parameters have been passed to it.

#### Examples

```js
function add(a, b, c) {
  return a + b + c;
}

var partialAdd = partial(add);

partialAdd(1)()()()(2, 3); // 6

function addAlot(a, b, c, d, e, f, g, h) {
  return a + b + c + d + e + f + g + h;
}

var partialAdd = partial(addAlot);

partialAdd()(1, 2)(3, 4)(5, 6)()()()()(6)()()(10, 11, 12); // 37

function subtractAlot(a, b, c, d, e) {
  return a - b - c - d - e;
}

var partialSub = partial(subtractAlot);

partialSub(1, 2, 3)(4, 5, 6); // -13
```

#### Hint

You will need to use closure as well as the length property on functions to solve this problem. The length property on functions allows you to see how many parameters a function accepts.

#### Solution

```js
function partial(cb) {
  var params = [];
  return function inner(...args) {
    params = params.concat(args);
    if (params.length >= cb.length) {
      return cb(...params.slice(0, cb.length));
    } else {
      return inner;
    }
  };
}
```

##### Tags

`#closure` `#hard` `#medium`
