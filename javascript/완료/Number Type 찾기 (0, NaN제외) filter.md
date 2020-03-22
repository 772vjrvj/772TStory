```
const arr = [{ id: 15 }, { id: -1 }, { id: 0 }, { id: 3 }, { id: 12.2 },
			{ }, { id: null }, { id: NaN }, { id: 'undefined' }, { id: false },
            { id: '' }, { id: ' ' }, { id: 'abc' }
            ]
const arrByID = arr.filter(filterByID);

console.log('Filtered Array\n', arrByID);

function getType(target) {
  return Object.prototype.toString.call(target).slice(8, -1);
}

function isNumber(target) {
  if (getType(target) === 'Number' && !isNaN(target))
    return true;
  return false;
}

//function isNumber(obj) {
//  return obj !== undefined && typeof(obj) === 'number' && !isNaN(obj)  
//참고 isNaN(null)은 false null이 일시적으로 0으로 된다. null 타입은 object
//}

let invalidEntries = 0;

function filterByID(item) {
  if (isNumber(item.id) && item.id !== 0) {
    return true
  }
  
  invalidEntries++;
  
  return false;
}
```

