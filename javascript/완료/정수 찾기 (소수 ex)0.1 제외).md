```
function getType(target) {
  return Object.prototype.toString.call(target).slice(8, -1);
}

function IntChk(a) {
  var reg=/[\.]/g; //소수( ex)1.1 제거)
    
	if (getType(a) !== 'Number' || isNaN(a) || reg.test(a)) {
		return false;
	}
    
	return true;
}

const array = ['string',new Number(),1.1,4, 6, 8, 9, 12, 53, {'a':'kkk1a'},
              '',' ',function(){},0,-17, 2, 5, 7, 31, 97, -1, 17, null,NaN, 
               1.1, undefined,false,true,new Boolean()
               ];
            
console.log(array.filter(IntChk));  
//[0, 4, 6, 8, 9, 12, 53, 0, -17, 2, 5, 7, 31, 97, -1, 17]
```

