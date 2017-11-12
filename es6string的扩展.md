#字符串
1. 提供了字符串的遍历接口
  ```javascript
  for(let aa of "aaa")
  {
  console.log(aa);
  };
  ```
2. 提供了新的方法查找，判断和生成字符串
    ```javascript
    var s = 'Hello world!';
    s.startsWith('Hello'); // true
    s.endsWith('!'); // true
    s.includes('o'); // true
    ```
#RegExp
1. es6中允许添加第二个修饰符(RegExp构造函数的第一个参数为正则表达式的前提下，并且会忽略之前原有表达式的修饰符。)
```javascript
 RegExp(/abc/ig,"i").flags;
//i
```
2. es6中添加了y修饰符，粘连修饰符。
  //g，y都是从全局匹配，后一次从上一次的匹配成功的下一个位置开始，但是g只要剩余中有即可，而y是从开头开始。
```javascript
var s = "aaa_aa_a";
var rex1 = new RegExp(/a+/,"g");
var rex2 = new RegExp(/a+/,"y");
rex1.exec(s);//aaa
rex2.exec(s);//aaa
rex1.exec(s);//aa
rex2.exec(s);//null
```
