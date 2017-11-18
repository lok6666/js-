1. 正则表达式是对字符串和特殊字符的一种逻辑公式，用来匹配字符串。
2. 正则表达式两种创建方式
  2.1. 字面量
     var  a = //gi;
  2.2. ##RexExp构造函数
     var a = new RegExp(//,"g(全局)i(忽略大小写)");
3. 正则表达式匹配字符串
  3.1. 字符串方法
  ```javascript
     "acac".replace(//gi,"x");
  ```
  3.2. 正则对象方法
  ```javascript
      var regExp = /a/gi;//思考如果加了g，循环了若干次后是true还是false，这是为什么？test中的lastIndex
       console.log(regExp.test("ab"));//true
       console.log(regExp.test("ab"));//false 为什么？
       console.log(regExp.test("ab"));//true
       console.log(regExp.test("ab"));//false 
   ```
4. 正则表达式相关字符
  4.1. \d匹配数字。“0\d\d”可以匹配“006”
  4.2. \w匹配任意字母或数字。"a\w"匹配"aa".
  4.2. 匹配任意字符。"a."匹配"as","aw","ar".
  4.4. +表示最少一个字符，？表示最多一个字符，*表示任意包含0个或多个。{n}表示n个字符，{n，m}n->m个字符。
  4.5. \s匹配一个空格。
  4.6. []表示范围，[abc]代表abc中任意一个字符。[^代表字符取反]，[^abc]代表非abc中的任意一个字符.
  4.7. -代表范围，[a-c3-6]。
  4.8. a|b匹配a或者b。
  4.9. ^表示行开头，^\d表示数字开头，$表示结束，\d$表示数字结尾。\b匹配单词边界。\B匹配非单词边界。
5. 切分字符串
   ```
   "ab c".split("");//
   ['a','b','','','c'];
   "ab;; c d".split(/[\s\,\;]+/);//
   ['a','b','c','d'];
    ```
6. 分组
  6.1. 用()表示的就是要提取的分组（Group)
  ```javascript
    console.log("NeeeNameName_11111".replace(/Name{3}/g,"X"));
    console.log("NameNameName_11111".replace(/(Name){3}/,"X"));
     NeeeNameName_11111
     X_11111
  ```
       
   6.2. exec()方法提取字串##
        exec()方法在匹配成功后，会返回一个Array，第一个元素是正则表达式匹配到的整个字符串，后面的字符串表示匹配成功的子串。
        exec()方法在匹配失败时返回null.
7. #贪婪匹配
  7.1. 正则表达式默认为贪婪模式，尽可能匹配多的字符。
      "12345678".replace(/\d{3,6}/,'X');//默认为贪婪模式  X78
      "12345678".replace(/\d{3,6}?/,'X');//设置为非贪婪模式 在量词后加？X45678
      "12345678".replace(/\d{3,6}?/g,'X');//返回什么？xx78
8. 正则表达式属性
  8.1. global 默认为false
  8.2. ignore case 默认为false
  8.3. multiline 默认为false
  8.4. lastIndex 表示当前匹配内容的最后一个字符的下一个位置
  8.5. sourse 正则表达式文本字符串
9. 原型方法
  9.1. test方法
  ```javascript
   var a = /\d\d/gi;
   console.log(a.test('124314a'));
  ```
  9.2. exec方法   
    //Part222 RegExp.prototype.exec 方法 可以获得更为详细的信息，返回一个有属性的数组，属性index表示匹配到的位置
    //对于非全局模式下返回第一个匹配的和所有的分组项，正则对象的lastIndex不起作用
    ```javascript
    var execExp = /\d{1,2}(\d)(\d)/;
    var retExp = execExp.exec("12s342dsfsf233s");
    console.log(retExp instanceof Array,retExp,execExp.lastIndex);
    true (3) ["342", "4", "2", index: 3, input: "12s342dsfsf233s"] 0
    ```
  9.3. search方法 
  ```javascript
    console.log("a1b2c3d4".search(/1/));//返回index 1
    console.log("a1b2c3d4".search(/f/));//返回index -1 没找到
    console.log("a1b2c3d4".search(/\d/g));//返回index 1 忽略全局
    console.log("a1b2c3d4".search(/\d\w/g));//返回index 1 忽略全局
  ```
  9.4 .match方法
    //String.prototype.match 如果匹配不到返回null 匹配到了返回数组
    // 包含的信息有index 原始字符串 有没有g影响很大
     ```javascript
    console.log("a1b2c3d4".match(/1/));//[ '1', index: 1, input: 'a1b2c3d4' ]
    console.log("a1b2c3d4".match(/f/));//null
    console.log("a1b2c3d4".match(/\d/));//[ '1', index: 1, input: 'a1b2c3d4' ]
    console.log("a1b2c3d4".match(/\d/g));//[ '1', '2', '3', '4' ]
    ```
  9.5 .replace方法
   ```javascript
    console.log("a,b,c,d".replace(",","X"));aXb,c,d
    console.log("a2b3c4d".replace(/[2-3]/,"X"));aXb3c4d
    console.log("a2b3c4d".replace(/[2-3]/g,"X"));aXbXc4d
   ```
