#es6中的let与const
1. let命令 
  1.1. let变量的声明只在let命令所在代码块{}内有用。(不可重名)
      let userId = 123;
    document.onclick = function () {
        console.log("userId = ",userId);
        //alert("userId = "+userId);
    };

    let a=2,b=3;
    if(a<b){
        let userId = 234;
    }
  1.2. let命令不能直接定义全局对象
    var x = 23;
    let y = 34;
    console.log(window.x,window.y);//23 undefined
  1.3. let可以避免变量共享
      for (var i = 0; i < 3; i++) {
            setTimeout(function() {
              console.log(new Date, i);
          }, 1000*i);
      }

      Tue Nov 07 2017 20:55:54 GMT+0800 (中国标准时间) 3
      Tue Nov 07 2017 20:55:55 GMT+0800 (中国标准时间) 3
      Tue Nov 07 2017 20:55:56 GMT+0800 (中国标准时间) 3
      for (let i = 0; i < 3; i++) {
          setTimeout(function() {
              console.log(new Date, i);
          }, 1000*i);
      }

      Tue Nov 07 2017 20:56:03 GMT+0800 (中国标准时间) 0
      Tue Nov 07 2017 20:56:04 GMT+0800 (中国标准时间) 1
      Tue Nov 07 2017 20:56:05 GMT+0800 (中国标准时间) 2
2. const命令
  2.1. const声明常量
    const PI = 3.1415926;
    console.log(PI);
    // PI = 3;//给常量再赋值 报错
  2.2.const声明时必须赋值,一旦声明必须立即初始化
    const foo;//报错
    const foo = 123;
  2.3. const作用域同let
    if(true){
      const MAX = 5;
    }
   //console.log(MAX);//报错
  2.4. const 除了声明常量外，也常用来声明不变的函数
      const fee = function () {

      };
  2.5. const指向引用对象不可改变，但是属性或者元素是可以改的
      const a = [];
      a.push(123,345);
      a.length = 1;
      a = "a";//报错
3. let,const特性
  3.1. let和const不存在变量提升
      console.log(a);//报错
      let a = 2;
      console.log(a);
  3.2. es6提升
      function f() {
        console.log("outside")
    };

    {
        f();
        {
            function f() {console.log("inside");}
        }
    }
    // 注意：不同的环境，存在兼容性问题
    // 考虑到环境导致的行为差异太大，应该避免在块级作用域内声明函数
    // 如果确实需要，也应该写成函数表达式，而不是函数声明语句
  3.3. 暂时性死区
      特性：1，只要块级作用域存在let，它所声明的变量就绑定了在这个区域，不受外部影响。
            2，let对这个块形成了封闭作用域，如果在声明之前使用这个变量，就会报错。
             if(true){
            tmp = "abc";
            let tmp;//思考如果改为var是否会报错，如果let tmp在上一行之前如何？
                     }
            typeof b;//报错 ReferenceError 需要使用前定义
            let b;//若没有此行，上一行是否会报错
            var tem = 123;
       
