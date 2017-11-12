#Math对象
##Math对象属性
  1. Math.E:即自然对数的底数，其值近似于 2.71828。
  2. Math.LN2:即 2 的自然对数，其值近似于 0.69314718055994528623。
  3. Math.LN10:即 10 的自然对数，其值近似于 2.3025850929940459011。
  4. Math.LOG2E:返回以 2 为底的 e 的对数（约等于 1.414）。
  5. Math.LOG10E:返回以10为底的对数（约等于0.434）。
  6. Math.PI:返回圆周率（约等于3.14159）。
  7. Math.SQRT1_2:返回返回 2 的平方根的倒数（约等于 0.707）。
  8. Math.SQRT2:返回 2 的平方根（约等于 1.414）。
##Math数值方法
  1. Math.random():返回0~1的随机数。
  2. Math.round():把数四舍五入到最接近的数字。
  3. Math.max(x,y):返回两个数中比较大的那个i
  4. Math.floor():向下取整。document.write(Math.floor(-5.9))：-6；
  5. Math.ceil():把数向上取整。
  6. Math.abs():返回数的绝对值。
##Math三角方法
  1. Math.sin().
  2. Math.cos().
  3. Math.asin().
  4. Math.acos().
#JSON对象
##JSON简洁：JSON是一种轻量级的数据交换格式，基于 ECMAScript的一个子集，使用完全独立于编程语言的文本格式来存储和传输数据。
##JSON与js对象的关系
  1. js中一切都是对象。
  2. json是js对象的字符串表现形式。
  ```javascript
  var obj4 = {x:1,y:2,a:[1,3,5],b:"xyz"};
  var json4 = '{"x":1,"y":2,"a":[1,3,5],"b":"xyz"}';
  var obj6 = [{z:3},[1,2]];
  var json6 = '[{"z":3},[1,2]]';
#JSON对象方法
##1. JSON.stringify(value,replacer?(控制筛选对象的键值),sapce(按缩进输出))
      var o2 = {
          a:[1,2],
          b:true,
          c:[3,4,"x",{y:34,z:56}],
      };
      //replacer 节点转换函数，在值被转为字符串之前转换树节点的值
      var jsonStr2 = JSON.stringify(o2,function (key,value) {
          if(value === true){
              value = false;
          }
          if((value instanceof Array)&&value.length == 4){
              value[0] = "Hi";
          }
          if(key === "a"){
              console.log("find key a");
              value = 12345;
          }
          if(key === "z"){
              console.log("find key z");
              value = "zzz";
          }
          return value;
      });
      console.log(jsonStr2);
      console.log(o2);
      find key a
      find key z
      {"a":12345,"b":false,"c":["Hi",4,"x",{"y":34,"z":"zzz"}]}
      {a: Array(2), b: true, c: Array(4)}
      ```
 ##2. JSON.parse(text,reviver)
 ```javascript
     var o6 = JSON.parse('{"p": 5}', function (k, v) {
        if(k === '') return v;     // 如果到了最顶层，则直接返回属性值，
        return v * 2;              // 否则将属性值变为原来的 2 倍。
    });                            // { p: 10 }
    console.log(o6);
    ```
