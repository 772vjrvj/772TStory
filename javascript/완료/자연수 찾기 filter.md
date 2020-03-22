```
function getType(target) {
  return Object.prototype.toString.call(target).slice(8, -1);
}

function NaturalNumChk(target) {
    const reg=/[\.]/g;
	if (getType(target) === 'Number' && !isNaN(target) && !reg.test(target) && target >= 1) {
		return false;
	}
}

const array = ['string',new Number(),1.1,4, 6, 8, 9, 12, 53, {'a':'kkk1a'},
              '',' ',function(){},0,-17, 2, 5, 7, 31, 97, -1, 17, null,NaN, 
               1.1, undefined,false,true,new Boolean()
               ];

console.log(array.filter(IntChk));  
//[4, 6, 8, 9, 12, 53, 2, 5, 7, 31, 9717]
```

