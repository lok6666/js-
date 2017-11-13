#Array.from()
//将类数组对象转化为数组
```javascrit
let arrayLike = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    length: 3
};
```
// ES5的写法
```javascript
var arr1 = Array.prototype.slice.call(arrayLike); // ['a', 'b', 'c']
```
// ES6的写法
```javascript
let arr2 = Array.from(arrayLike); 
```
#Array.of()
//将一组值转化为数组
```javascript
Array.of(3);
//[3];
```
//这个方法的目的为了解决Array()的不足，参数的不同，会导致Array()返回结果不同。
```javascript
Array(); // []
Array(3); // [, , ,]
Array(3, 11, 8); // [3, 11, 8]
```
#Array新增原型方法
##Array.copyWithin(target,start,end):指定位置成员复制其他位置。
//target:从该位置开始替换数据。
//start:从该位置开始替换数据。
//end:从该位置停止读取数据。
```javascript
[1,1,2,3,54].copyWithin(1,3);
//[1, 3, 54, 3, 54]
```
##Array.find(function(value, index, arr){}):找出第一个符合条件的数组成员。
//value:当前值。
//index:当前位置。
//arr:原数组。
```javascript
[1, 5, 10, 15].find(function(value, index, arr) {
    return value > 9;
}); // 10
```
##Array.fill(value,index,end):填充数组
//value:数值。
//index:用于填充起始位置。
//end:结束位置。
```javascript
[1,2,3,4].fill(5,2,3);
//[1, 2, 5, 4];
```
##Array.includes(value, index):返回一个布尔值，表示某个数组是否包含给定的值。
//index:搜索起始位置，若为负数表示倒数的开始。
```javascript
[1, 2, 3].includes(3, -1); // true
[1,2,3].includes(1);//true
```
##遍历数组的三个方法
###entire()
```javascript
for (let [index, elem] of ['a', 'b'].entries()) {
    console.log(index, elem);
}
```
###keys()
```javascript
for (let index of ['a', 'b'].keys()) {
    console.log(index);
}
```
###values()
```javascript
for (let elem of ['a', 'b'].values()) {
    console.log(elem);
}
```
##//如果不使用for...of循环，可以手动调用遍历器对象的next方法，进行遍历。iterator参见后续章节
```javascript
let letter = ['a', 'b', 'c'];
let entries = letter.entries();
console.log(entries.next().value); // [0, 'a']
console.log(entries.next().value); // [1, 'b']
console.log(entries.next().value); // [2, 'c']
```
##Array空位数组（稀疏数组）
//forEach(), filter(), every() 和some()都会跳过空位。
//map()会跳过空位，但会保留这个值
//join()和toString()会将空位视为undefined，而undefined和null会被处理成空字符串。
new Array(3);// [, , ,]
//空位不是undefined，一个位置的值等于undefined，依然是有值的。空位是没有任何值，in运算符可以说明这一点。
0 in [undefined, undefined, undefined] // true
0 in [, , ,] // false

//单独测试下述代码
```javascript
// forEach方法
[,'a'].forEach(function(x,i){return console.log(i);}); // 1

// filter方法
['a',,'b'].filter(function(x){return true;}) // ['a','b']

// every方法
[,'a'].every(function(x){return x==='a'}) // true

// some方法
[,'a'].some(function(x){return x !== 'a';} ) // false

// map方法
[,'a'].map(function (x) {return 1;}) // [,1]
```
