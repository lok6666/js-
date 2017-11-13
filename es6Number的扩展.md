#Number.isFinite()
//检验是否为有限的(finite)
```javascript
Number.isFinite(1);//true
Number.isFinite(0.5);//true
Number.isFinite(NaN);//true
```
#Number.isNaN()
//检验是否为有限的NaN
```javascript
Number.isNaN(NaN);//true
Number.isNaN(1);//false
Number.isNaN(9/NaN); // true
Number.isNaN('true'/0); // true
Number.isNaN('true'/'true') // true
```
##与传统的isFinite(),isNaN()相比，传统方法先打 非数值转化为数值。
```javascript
isFinite(25); // true
isFinite("25"); // true
Number.isFinite(25); // true
Number.isFinite("25"); // false
isNaN(NaN); // true
isNaN("NaN"); // true
Number.isNaN(NaN); // true
Number.isNaN("NaN"); // false
```
#Number.parseInt()
//转化为整数
```javascript
Number.parseInt(12.3);//12
```
#Number.parseFloat()
//转化为浮点类型
```javascript
Number.parseFloat("123.45#");//123.45
```
##与传统的parseInt(),parseFloat()相同。
//这样做的目的，是逐步减少全局性方法，使得语言逐步模块化。
```javascript
Number.parseInt === parseInt // true
Number.parseFloat === parseFloat // true
```
##Number.isIntger()
//判断是否为整数
```javascript
Number.isInteger(25); // true
Number.isInteger(25.0); // true
Number.isInteger(25.1); // false
```
#Math.trunc()
//去除小数部分，返回整数部分
```javascript
Math.trunc(-7.9);//-7
Math.trunc(3.1);//3
```
#Math.sign()
//判断是正数，负数，还是零
```jvascript
Math.sign(-5); // -1
Math.sign(5); // +1
Math.sign(0); // +0
Math.sign(-0); // -0
Math.sign(NaN); // NaN
Math.sign('foo'); // NaN
Math.sign(); // NaN
```
