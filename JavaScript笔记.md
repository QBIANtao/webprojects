# 数组

#### 1：数组去除数组指定元素(代码里是删除为0的元素)，形成新数组（这里用的是三元没有用if else）。

```javascript
<script>
            var arr1 = [2, 0, 6, 1, 77, 0, 52, 25, 7];
            var arr2 = [];
            for (var i = 0; i < arr1.length; i++) {
                // if (arr1[i] != 0) {
                //     arr2[arr2.length] = arr1[i];
                // }
                arr1[i] != 0 ? (arr2[arr2.length] = arr1[i]) : (arr1[i] = arr1[i]);
            }
            console.log(arr2);
            console.log(arr1);
        </script>
```



#### 2:筛选数组(这里是选出大于等于10的元素组成新数组，利用了arr2. length属性让arr2数组索引从0开始)

```javascript
<script>
            var arr1 = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
            var arr2 = [];
            for (var i = 0; i < arr1.length; i++) {
                if (arr1[i] >= 10) {
                    arr2[arr2.length] = arr1[i];
                }
            }
            console.log(arr2);
        </script>
```



#### 3:翻转数组(arr1.length-1是因为索引比length少1)

```javascript
  <script>
            var arr1 = ['red', 'green', 'blue', 'pink', 'purple'];
            //把内容反过来存放
            var arr2 = [];
            for (var i = arr1.length - 1; i >= 0; i--) {
                arr2[arr2.length] = arr1[i];
            }
            console.log(arr2);
        </script>
```

 

#### 4:数组转换为分割字符串

```javascript
<script>
            var arr = ['red', 'green', 'blue', 'pink'];
            var str = '';
            for (var i = 0; i < arr.length; i++) {
                str += arr[i] + '|';
            }
            console.log(str);
        </script>
```



#### 5:数组新增元素案例(这里利用数组长度作为索引符号)，i+1保证数组第一个数字为1。

```javascript
 <script>
            var arr = [];
            var length = parseFloat(prompt('请输入数组长度'));
            for (var i = 0; i < length; i++) {
                arr[i] = i + 1;
            }
            console.log(arr);
        </script>
```



#### 6:算法：冒泡排序，交换左右两个数组元素。

```javascript
   <script>
            var arr = [3, 2, 4, 5, 1];
            //外循环控制趟数,根据数字数需要交换arr.length-1趟
            for (var i = 0; i < arr.length; i++) {
                for (var j = 0; j < arr.length - i; j++) {
                    //内循环控制两个数字之间交换次数,第一次交换会使得数组最后一个数为最大值,则下一次交换则会忽略最后一个数,依次减次数.
                    if (arr[j] > arr[j + 1]) {
                        var temp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = temp;
                        //临时变量temp来保存两个交换的变量值
                    }
                }
            }
            console.log(arr);
        </script>
```

![](C:\Users\Biantao\Desktop\v2-33a947c71ad62b254cab62e5364d2813_b.gif)

## 函数

#### 1：概念

封装了一段可以重复执行的代码块。目的是让大量代码重复使用。



#### 2：函数的使用

```javascript
<script>
            // 1:声明函数:function +函数名(){
            //     函数体
            // }
            // 2:函数名为动词
            // 3:函数不调用,自己不执行
            // 4:调用函数:函数名();
            function sayhi() {
                console.log('hi');
            }
            sayhi();
        </script>
```

例子:

```javascript
<script>
            function getSum() {
                var sum = 0;
                for (var i = 0; i <= 100; i++) {
                    sum += i;
                }
                console.log(sum);
            }
            getSum();
//求和1-100
        </script>
```

#### 3：函数的参数

##### 形参和实参

```javascript
   <script>
            //1:函数可以重复相同的代码
            // function cook() {
            //     console.log('酸辣土豆丝');
            // }
            // cook();
            // function name(形参1, 形参2) {} //声明函数的小括号里是形参 (形式上的参数)
            // 函数名(实参1, 实参2); //在调用函数的小括号里是实参(实际的参数);

            // 3:形参和实参的执行过程
            function cook(aru) {
                // 形参是接收实参的 aru='酸辣土豆丝',形参类似变量
                console.log(aru);
            }
            cook('酸辣土豆丝');
            cook('大肘子');
            // 4:函数的参数可以有也可以没有,个数不限
        </script>
```

###### 形参个数和实参个数不匹配的问题:

| 参数个数             | 说明                            |
| :------------------- | :------------------------------ |
| 实参个数多于形参     | 忽略多出的形参                  |
| 实参个数少于形参     | 少的形参视为undefined,相加为NaN |
| 实参个数等于形参个数 | 输出正确结果                    |

```javascript
 <script>
            function getSum(num1, num2) {
                console.log(num1 + num2);
            }
            // 1:形参个数和实参一致:正常输出结果
            getSum(1, 2);
            // 2:如果实参个数多于形参:会取到形参的个数
            getSum(1, 2, 3);
            // 3:实参的个数小于形参的个数:多余的形参被定义成undefined 结果是NaN
            // 形参可以看作是不用声明的变量 num2是一个变量但是没有接收值 结果是undefined
            getSum(1); //NaN
            // 尽量让实参和形参相匹配
        </script>
```

<u>注意：形参不传值，默认是Undefined。</u>

#### 4：函数的返回值：return语句

```javascript
  <script>
            // 1:函数是做某件事或者实现某种功能
            function cook(aru) {
                return aru;
            }
            console.log(cook('大肘子'));
            // 2:函数的返回值格式
            // function 函数名() {
            //     return 需要返回的结果;
            // }
            // 函数名();
            // (1)我们函数只是实现某种功能,最终的结果需要返回给函数调用者 通过return实现
            // (2)只要函数遇到return,就把后面的结果返回给调用者 函数名()=return后面的结果
            function getResult() {
                return 666;
            }
            getResult(); //getresult()=666;
            console.log(getResult());
            //4:求任意两个数字的和
            function getSum(num1, num2) {
                return num1 + num2;
            }
            console.log(getSum(1, 2));
        </script>
```

##### 三元运算符return

```javascript
<script>
            function getMax(num1, num2) {
                return num1 > num2 ? num1 : num2;
    //return写在三元运算符前面
            }
            console.log(getMax(10, 31));
            console.log(getMax(10, 9));
        </script>
```

##### 求任意数组最大值return

```javascript
  <script>
            function arrGetMax(Arr) {
                var Max = Arr[0];
                for (var i = 0; i < Arr.length; i++) {
                    if (Arr[i] > Max) {
                        Max = Arr[i];
                    }
                }
                return Max;
            }
            var re = arrGetMax([1, 23, 4, 101, 999]);
            console.log(re);
        </script>
```

##### return注意事项

###### 1：return会终止函数，return后面代码不会执行。

```javascript
 <script>
            // 返回值注意事项
            // 1:return 终止函数
            function getSum(num1, num2) {
                return num1 + num2; //return后面代码不会执行
                alert('我是不会被执行的哦');
            }
            console.log(getSum(1, 2));
        </script>
```

###### 2:return只能返回一个值，如果是多个，返回最后一个

```javascript
<script>
console.log(getSum(1, 2));
            // 2:return只能返回一个值
            function fn(num1, num2) {
                return num1, num2;
            }
            console.log(fn(1, 2));
        </script>
```

###### 3:return输出多个值的方法

```javascript
<script>         
            function getResult(num1, num2) {
               //3:利用数组保存+-*/的值
                return [num1 + num2, num1 * num2, num1 / num2];
            }
            var re = getResult(10, 20); //返回的是一个数组
            console.log(re);
        </script>
```

###### 4：函数没有return则返回undefined

```javascript
<script>   
   //4:我们函数如果有return,则返回的是return后面的值,没有return,则返回
            // undefined
            function fun1() {
                return 666;
            }
            function fun2(params) {
                //没有return
            }
            console.log(fun1()); //返回666
            //
            console.log(fun2()); //没有return,返回undefined
        </script>
```

###### 5：函数判断素数

```javascript
<script> 
var num = parseInt(prompt('请输入一个数字'));
            function getPrimenumber(a) {
                var p = 1; //1是质数,0不是质数
                for (var i = 2; i < a; i++) {
                    //这里因为所有数都能被1整除,所以从2开始到输入的数字本身之间用循环来判断有没有能整除的数
                    if (a % i == 0) {
                        p = 0;
                        break;
                    }
                }
                if (p == 1) {
                    return '是质数';
                } else {
                    return '不是质数';
                }
            }
            alert(getPrimenumber(num));
        </script>
```



#### 5:break、continue、return的区别

break:结束当前循环体;

continue:跳出本次循环;

return:不仅可以退出循环，还能够return语句中的值，同时还可以结束当前函数体内的代码。

#### 6：透过榨汁机看透函数

![image-20211031190654141](C:\Users\Biantao\AppData\Roaming\Typora\typora-user-images\image-20211031190654141.png)



#### 7：arguments的使用

###### 1：arguments的定义

当我们不知道有多少参数传递的时候，可以用arguments来获取。它是当前函数的一个内置对象，所有函数都有，arguments对象中存储了传递的所有实参。

###### 2：格式

```javascript
function 数组名(){
    console.log(arguments)
}
数组名(任意实参);
//不知道几个实参时候，可以输入任意实参，以伪数组形式保存在arguments里。
```



###### 3：特点

1：是伪数组并不是真正意义上的数组

2：有数组的length属性，可以获取长度

3：按照索引方式存储，可以遍历

4：没有真正数组的一些方法，如pop()、push()

注意：只有函数才有arguments属性，所有函数都内置arguments。

#### 8：函数常用封装名

reverse：翻转

sort：冒泡

#### 9：函数调用另一个函数

函数都是独立模块，他们之间可以互相调用

```javascript
<script>
            function fn1() {
                console.log(11);
                fn2(); //fn1函数里调用了fn2函数
            }
            fn1();
            function fn2() {
                console.log(22);
            }
        </script>
```

调用函数判断年份2月是什么年有多少天

```javascript
<script>
            function backDay() {
                var year = parseInt(prompt('请输入年份'));
                if (leapYear(year)) {
                    alert('闰年，2月29天');
                } else {
                    alert('不是闰年,2月28天');
                }
            }
            function leapYear(year) {
                var flag = false;
                if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
                    flag = true;
                }
                return flag;
            }
            backDay();
        </script>
```

#### 10:函数的两种声明方式

###### 1:关键字定义函数

###### 2：函数表达式（匿名函数）

```javascript
<script>
            // var 变量名 = function () {};
            // 2:函数表达式(匿名函数)
    
            var fun = function (aru) {
                console.log(aru);
            };
            fun('pink老师');//用函数表达式的变量名来调用，同样可以是输入实参
            // 1:fun是变量名
            // 2：函数表达式根声明变量差不多，变量里面存值，函数表达式里面存函数
// 3:函数表达式也可以传递参数
        </script>
```



## JavaScript的作用域

#### 1:概念

代码名字(变量)在某个范围内起作用和效果，目的是为了提高程序的可靠性，更重要的是减少命名冲突。

#### 2：作用域种类（ES6之前)

##### 1：全局作用域

整个script标签或者是一个单独的script文件

##### 2：局部作用域(函数作用域)

函数内部就是局部作用域，可以理解为这个代码名字只在函数内部起效果

注意：不同作用域下不会冲突

#### 3:变量的作用域

##### 1：全局变量

###### 1：概念

在全局作用域下的变量，全局都可以使用

```javascript
<script>
    var num=1;//num是一个全局变量
    </script>
```

###### 2：两种全局变量

函数内部没有声明(var)直接赋值的变量也是全局变量

```javascript
<script>
    function fn(){
    num=1;//没有var声明直接赋值他也是一个全局变量
}
console.log(num)
输出结果为1
    </script>
```

##### 2：局部变量

###### 1：概念

在局部作用域下的变量，函数内部的变量

```javascript
<script>
    function fn2(){
    var num2=1;//这是一个局部变量，只能在函数内部使用
}
console.log(num2);//这里输出为undefined没有数值
    </script>
```



###### 2：函数的形参也是局部变量

##### 3：全局变量和局部变量的执行效率

1：全局变量只有在浏览器关闭的时候才会销毁，比较占用内存资源

2：局部变量当我们程序执行完毕就会销毁，比较节约内存资源

#### 4：作用域链

##### 1：概念

内部函数访问外部函数的变量，采用的是链式查找的方式来决定取哪个值，这种结构我们称为作用域链

```javascript
<script>
    var num=1;
    function fn(){
	var num=2;//外部函数
        function fn2(){
            //内部函数
            console.log(num);//这里取的最近fn函数里的num=2；
}
    }
    
    </script>
```

##### 2：就近原则

```javascript
<script>
    var num =10;
    	function fn(){
            var num=20;//外部函数
             function fun(){
                 console.log(num)//内部函数
             }
            fun();//这里也需要调用内部的函数
        }
    fn();//调用函数根据链式输出的为20
    </script>
```

##### 3：案例

```javascript
<script>
    var num1=1;
		function fn1(){
            var num1=11;
            var num2='22';
            function fn2(){
                var num1=12;
                 function fn3(){
                     console.log(num1);
                     console.log(num2);
                 }
                fn3();
            }
            fn2();
        }
    
    
    fn1();//输出为
    </script>
```

