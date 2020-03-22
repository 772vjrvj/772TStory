```
<!DOCTYPE html>
<html>
<body>
  <p>Hello</p>
  <script>
    function getType(target) {
      return Object.prototype.toString.call(target).slice(8, -1);
    }

    function isString(target) {
      return getType(target) === 'String';
    }

    function isElement(target) {
      return !!(target && target instanceof HTMLElement);
      // 또는 `nodeType`을 사용할 수도 있다.
      // return !!(target && target.nodeType === 1);
    }

    // HTMLElement를 상속받은 모든 DOM 요소에 css 프로퍼티를 추가하고 값을 할당한다.
    function css(elem, prop, val) {
      // type checking
      if (!(isElement(elem) && isString(prop) && isString(val))) {
        throw new TypeError('매개변수의 타입이 맞지 않습니다.');
      }
      elem.style[prop] = val;
    }

    css(document.querySelector('p'), 'color', 'red');
    css(document.querySelector('div'), 'color', 'red');
    // TypeError: 매개변수의 타입이 맞지 않습니다.
  </script>
</body>
</html>
```

Lodash 자바스크립트 라이브러리를 사용할 수도 있다. _.isElement

https://lodash.com/



https://poiemaweb.com/js-type-check



MDN nodeType

https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType

