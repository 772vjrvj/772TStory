```
<!DOCTYPE html>
<html>
<body>
  <ul>
    <li></li>
    <li></li>
    <li></li>
  </ul>
  <script>
    const isArrayLike = function (collection) {
      // 배열 인덱스: 32bit 정수(2의 32제곱 - 1)
      // 유사 배열 인덱스: 자바스크립트로 표현할 수 있는 양의 정수(2의 53제곱 - 1)
      const MAX_ARRAY_INDEX = Math.pow(2, 53) - 1;
      // 빈문자열은 유사배열이다. undefined == null => true
      const length = collection == null ? undefined : collection.length;
      return typeof length === 'number' && length >= 0 && length <= MAX_ARRAY_INDEX;
    };

    // true
    console.log(isArrayLike([]));
    console.log(isArrayLike('abc'));
    console.log(isArrayLike(''));
    console.log(isArrayLike(document.querySelectorAll('li')));
    console.log(isArrayLike(document.getElementsByName('li')));
    console.log(isArrayLike({ length: 0 }));
    (function () {
      console.log(isArrayLike(arguments));
    }());

    // false
    console.log(isArrayLike(123));
    console.log(isArrayLike(document.querySelector('li')));
    console.log(isArrayLike({ foo: 1 }));
    console.log(isArrayLike());
    console.log(isArrayLike(null));
  </script>
</body>
</html>
```

Lodash isArray를 사용해도 된다. _.isArray

