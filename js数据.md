# summarize
## js数据类型，值，及其转换
        1. js分为基本数据类型，和引用类型。基本数据对象分为NUmber（NaN类型为NUMber，两个NaN不相等），String，Boolean，underfined，Null。引用对象分为Function，Array，Date，Error。（注：NUll类型为对象。引用对象类型为方法。Math，Json为对象。）
        2. js基本对象的变量基本在栈区。引用类型的变量引用分配在堆区，引用的对象（个人理解为指针）分配在堆区。
        3. js对象检测方法为typeof，instanceof。
        4. 两者区别在于内存分配方式的不同，赋值的不同（基本类型是值得传递，引用类型是引用赋值），判断相等的不同（引用对象的属性放在堆区，是值得判断），函数参数传递的不同（基本类型是值得传递，引用类型是引用传递），内存分配方式是变量的生命周期。 
         ```javascript
                var obj_a = {value:1};
                function fn_a(arg){
                    arg.value=3;
                };
                fn_a(obj_a);
                console.log(obj_a);// 这时候obj_a是{value:3}
                function fn_b(arg){
                    arg={value:2};//创建了一个新的对象，arg指向新对象
                };
                fn_b(obj_a);
                console.log(obj_a);// 这时候obj_a是{value:3}
                ）。
         ```
        5. 对象的方法源于prototype。对象的--proto--与prototype是同一个东西。
        6. 基本数据类型设置临时对象属性,不影响基本值。     
                ```javascript
                var str = "aaaaaa";
                str.length=2;
                console.log(str);
                ```
        7. 其他类型转化为布尔，underfined->false,null->false,0,NaN->false,"->false,其他都为true。
