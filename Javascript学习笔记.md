# Javascript基础学习笔记

## 1 javaScript历史

### 1-1 JavaScript能做什么

万金油，无所不能。

- 表单动态校验（密码强度检测）( JS 产生最初的目的）
- 网页特效。
- 小程序
- 服务端开发（ Node.js )。
- 桌面程序（ Electron )（像你们用的vscode就是基于js开发的）。
- App ( Cordova )。
- 控制硬件﹣物联网（ Ruff )。
- 游戏开发（cocos2d-js）。

### 1-2 ECMAScript脚本语言

1、JavaScript,JScript等脚本语言都是基于ECMAScript标准实现的，因此在`声明变量`,`操作数组`等语法是完全一样的。

2、但在操作页面上的元素和操作浏览器方面各有各自独特的方法，因而BOM和DOM的实现各个厂商是不一样的。

3、JavaScript由ECMAScript，DOM和BOM三者组成的。



一般认为**浏览器**中JavaScript由三部分组成

- ECMAScript: 基础语法
- DOM: 文档对象模型
- BOM: 浏览器对象模型



![img](https://cdn.nlark.com/yuque/0/2022/png/327963/1662713129085-6a605a62-55cb-4988-8ab4-4f54bfe8f45c.png)

## 2 Hello World

### 2-1 引入

写script标签。

```javascript
    <script>
        alert('hello world')
    </script>
```

### 2-2 prompt

prompt可以弹出一个消息框， 你可以输入信息，然后我们的js可以获取到你输入的信息属于BOM api。

```javascript
const data = prompt('请输入你的姓名：')
```

### 2-3 console.log()

console.log()用于在控制台打印信息，他常常用于调试代码属于BOM apil

```js
console.log(data)
```

### 2-4 alert 

alert 用于弹出提示框，属于BOM api。

```javascript
alert(data+'你好')
```

- 注意：alert() 主要用来显示消息给用户，console.log() 用来给程序员自己看运行时的消息

## 3 数据类型

有七种

- 数字 number
- 字符串 string
- 布尔 bool
- 符号 symbol
- 空 undefined
- 空 null
- 对象 object

总结:四基两空一对象

### 3-1 数字 number

64位浮点数

**写法**

- 整数写法：1
- 小数写法：0.1
- 科学计数法：1.23e4
- 八进制写法(用得少)：0123 或 00123 或 0123
- 十六进制写法：0x3F 或 0X3F
- 二进制写法：0b11 或 0B11

```javascript
    //数字number 64浮点数
    let number1 = 1 //整数声明
    let number2 = 0.1 //声明小数
    let number3 = 1.23e100 //科学计数法
    let number4 = 0b11 //2进 制写法
    let number5= Infinity //无穷大
    let number6 = NaN //无法被表示的数字
    let n = '你好'-1 //NaN 
    let n2 = 0/0 //NaN0/0
    console.log(n);
    console.log(n2);
    console.log(Number.MAX_VALUE);
    //因为js的精度问题，0.1+0.2结果不等于0.3而等于0.300000000000004
    console.log(0.1+0.2);
```

字符串转Number，可以用Number()进行转换。

```javascript
    let phoneNumber = '1845454554565'
    let phoneNumber = Number(phoneNumber)
    console.log(phoneNumber);
```

数字运算：四则运算+-*/

```javascript
    let number1 = 1 //整数声明
    let number2 = 0.1 //声明小数
	let add = number1 + number2 //1.1
    let del = number1 - number2 //0.9
    let mul = number1 * number2 //0.1
    let divide = number1 / number2  //10
```

取余%

```javascript
    let dat = 123
    let dd = 10
    let mod = dat%dd // 3 
    console.log(mod);
```



### 3-2 字符串string

let和const声明变量

```javascript
    let name= '大帅比'
    const name2= 'kkk'
    name =  'wwww'
    console.log(name);
    //无法去修改一个常量的值
    name2= 'dddd '
    console.log(name2)
```



```javascript
    let name = '大帅比'
    let name2 = 'klkl'
    let phoneNumber = '1845454554565'
    // 通过length可以获取字符串的长度
    console.log(name.length);//3
    console.log(name[1]); //获取帅
    console.log(phoneNumber.substring(7,11)); //通过substring截取字符串
```



### 3-3布尔bool

bool用来判断true或者false它一般和if条件判断搭配使用。

```javascript
    let bool = true
    let a = 1
    let b ='1'
    // ==不判断类型===会判断数据类型
    let bool2=a==b //true
    let bool3=a===b //false
    console.log(bool2);
    console.log(bool3);
```

js中的falsy值， 会被if判断为false，!将bool取反，false->true true ->false

```javascript
if(!undefined){
        console.log('undefined为fasly值');
    }

    if(!NaN){
        console.log('NaN为fasly值');
    }

    if(!null){
        console.log('null为fasly值');
    }

    if(!0){
        console.log('0为fasly值');
    }

    if(!''){
        console.log('""fasly值');
    }

```





### 3-4 空undefined,null 

如果一个变量，声明了，但是我们没有给它赋值，默认为undefined。

```javascript
    let c
    console.log(c);
```

在我们还不确定a的值的时候，先给一个null来占位。

```javascript
let a = null
```

### 3-5 对象0bject

对象常常用来描述一个事物，对象里面可以包含所有的数据类型。

```javascript
    let friend={
        name:'钱多多',
        age:26 ,
        hobbies:['游戏','旅游'],
        isMale:true
    }
```

关于对象的操作

通过.操作符来获取对象中的属性能够获取到key对应的value值

```javascript
    const name = friend.name //钱多多
    console.log(name);
    const name2 = friend['name'] //使用[]写法， 获取到value
    console.log(name2) ;
    // .一个不存在的属性，结果为undefined 
    console.log(friend.b);
    //删除key会 将key连同它的value-起删除
    delete friend['age']
    console.log(friend);
    //获取对象的所有的key值
    const keys = Object.keys(friend)
    console.log(keys);
    //获取对象所有的value值
    const values = Object.values(friend)
    console.log(values);
```

### 3-6符号symbol 

## 4 原型

### 4-1 做一个实验

```javascript
        let obj={
            a:1
        }
        console.log(obj.b);
```

程序正常运行了，obj上有这个toString的属性。

![image-20230819095229547](C:\Users\Dongdong\AppData\Roaming\Typora\typora-user-images\image-20230819095229547.png)

我们在obj的prototype里发现了这个属性，那么你会有疑问，为什么我声明的对象里，会多出这样的一堆属性，它们是如何添加进去的，下面我们来探究这个问题。



### 4-2 对象的prototype是怎么来的

我们可以画一个图

![img](https://cdn.nlark.com/yuque/0/2023/png/8435413/1686017978280-497b27cd-4262-481d-803d-f781c5f25699.png)

首先我们要知道

- 在你的js代码还没有运行的时候，js环境里就有一个window对象了

- window对象里有一个Object属性，Window.Object是一个函数对象

  ![](C:\Users\Dongdong\AppData\Roaming\Typora\typora-user-images\image-20230819095808545.png)

- window.Object这个对象中，有一个属性，叫prototype
- window.Object.prototype里有toString等属性

上图表述了这个过程，在最开始的时候，js就在window这个全局对象里，做了这些事情。



下面我们用hasOwnProperty用来判断，我们的对象中是否含有某个属性。是用来判断是否含有你对象本身的属性，而不含原型属性。

```javascript
        let obj={
            a:1
        }
		console.log(obj.hasOwnProperty('a'));   //true
        // in用来判断，对象中是否含有某个属性，包含原型属性
        console.log(toString in obj);  //false
```

## 5 类型转换

### 5-1 String转Number

特点:只能识别纯数字的字符串包括整数，小数，科学计数法。

```javascript
        let a = Number('10')
        let b = Number('Hello')
        let c = Number (undefined)
        let d = Number('1.23e15')
        console.log(a); //10
        console.log(b); //NaN
        console.log(c); //NaN
        console.log(d); //1230000000000000
```

parseInt（转整数）和parseFloat（转浮点数）

parseInt (string, radix)，radix进制默认10，string不为数字返回NaN

```javascript
        let n = parseInt('16px')
        console.log(n); //16
```

### 5-2 Number转String

用to.String()

```javascript
        let a = Number('10')        
		let aStr = a.toString()
        console.log(aStr);  //10
```

### 5-3 Bool转Number

true--->1   false---->0

```javascript
        let boolN = Number(true)
        let boolF = Number(false)
        console.log(boolN); // 1
        console.log(boolF); // 0
```

### 5-4 Number转Bool

0--->false  除0以外的数--->true

```javascript
        let e = 0
        let f = 6
        let bool1 = Boolean(e)
        let bool2 = Boolean(f)
        console.log(bool1); //false
        console.log(bool2); //true
```



### 5-5 Object转String

也是用toString()进行转换。

```javascript
        let obj = {
            a:3,
            b:5
        }

        const objStr = obj.toString()
        console.log(objStr); //[object Object]
```

序列化JSON.stringify 将对象转字符串

```javascript
        const objStr2 = JSON.stringify(obj)
        console.log(objStr2); //{"a":3,"b":5}
```

## 6 运算符

### 6-1 四则运算+-\*/

```javascript
        let a = (55-60)+20
        let b = 12
        let c = 13
        let d = '12' 
        //比较> < >= <= 1=(等价于-不判断类型) !==(等价===判断类型的)
        console.log(b > c);     //false
        console.log(b < c);     //true
        console.log(b != c);    //true1og
        console.log(b != d);    //false 
        console.log(b !== d);  //true
```

### 6-2 逻辑运算

与：&&当且仅当两边都为true才返回true

或：||一边为true,返回true

非：!取反

```javascript
        let d = '12' 
        let e = 0
        console.log(e && d);  //0 
        console.log(e || d);  //12
        console.log(!e);     //true
```

### 6-3 三元表达式a?b:c* 

*a如果为true,返回b，否则返回c* 

```javascript
        let abc=(20 > 6) ? 10:4
        console.log(abc); // 10
        console.log(abc); // 4
```

# 7 控制语句

if else如果,就

条件表达式，if中的内容如果为true 就执行代码块1如果为false,执行代码块2

示例代码1：

```javascript
        const condition = 6>4
        if(condition){
        // 代码块1
            alert( 'yes')
        }else{
        // 代码块2
            alert('no')
        }

        const score = prompt('请输入你的分数：')
        if(score>=60){
            alert('及格啦')
        }else{
            alert('不及格')
        }
```

示例代码2：

```javascript
 let a = 20
        // if else if else 10<age<18
        if(a > 10){
        //当a>10
        // a<18的时候，进入代码块1
            alert('少年')
        }else if(a > 18){
        // a>18的时候， 进入代码块2
            alert('青年')
        }else{
        //小于10的时候，进入代码块3
            alert('幼年')
        }
```

## 7-1 小练习1

题目：
输入工作年限

​    1.如果你的工作年限小于1年，你的年假是5天

​    2.如果你的工作年限小于3年,你的年假是7天

​    3.如果你的工作年限大于等于3年，你的年假是15天

示例代码：

```javascript
        let workYears = prompt('请输入你的工作年限：')

        // 你的年假,初始化为null
        let hoilday = null
        if(workYears < 0){
            hoilday = 0
        }else if(workYears < 1){
            hoilday = 5
        }else if(workYears < 3){
            hoilday = 7
        }else if(workYears >= 3){
            hoilday = 15
        } 
		//弹出对话框
        alert('你的年假是'+ hoilday)
```

## 7-2 switch-case

switch case传入一个变量,判断这个变量，是否符合case中的条件，符合条件，就执行下面的代码块，每个代码块用break。

swith结构

```javascript
switch语句用来定义多分支条件语句,语法如下:
	switch(表达式){
    case 值1:
      执行体1;
      break;
      
    case 值2:
      执行体2;
      break;
    ...
    default:
    	默认执行体;
      break; //default语句中break可有可无。
  }
```

​    小练习

​    1.输入你用的手机

​    2.如果输入的是苹果，alert('土豪')

​    3.如果是华为,alert('战狼')

​    4.如果是小米,alert(小米**) 

```javascript
        const phone = prompt('请输入你的手机牌子：')
        const resName = phone.slice(0,2)
        switch (resName) {
            case '苹果':
                alert('土豪')
                break;
            case '华为':
                alert('战狼')
                break;
            case '小米':
                alert('小米**')
                break;
            default:
                alert('不认识你的杂牌子手机')
                break;
        }

```

## 7-3 for循环

### 7-3-1 表达式

```javascript
for (initialization; condition; afterthought)
  statement
```

js中的for循环，1.声明一个变量i 2.i的取值范围 3.累加器

### 7-3-2 结构

```javascript
#结构: if--else--   如果--否则--
if(条件表达式){
   代码块1
}else{
   代码块2
}
#注: 条件表达式为true,执行代码块1
     条件表达式为false,执行else中的代码块2
```



### 7-3-3 遍历数字

求和1-100

```javascript
        let sum =0
        for(let i=0;i<=100;i++){
            sum += i
        }
        alert('1到100的和为'+sum)  //弹出对话框，显示和为5050
```

### 7-3-4 遍历对象

```javascript
let obj = {
            a:2,
            b:5,
            c:9,
        }
        for(const property in obj){
            console.log(property);
            const value = obj[property]
            console.log(value);       
        }
```

得到结果

![image-20230819112124533](C:\Users\Dongdong\AppData\Roaming\Typora\typora-user-images\image-20230819112124533.png)

## 7-4 小练习2

​	1.输入一个大于0的数字

​    2.alert() 这个数字是否为质数

​    质数只能整除1和它自身的数，%



实现代码：

```javascript
        let num = prompt('请输入一个数：')
        for(let i = 1;i<num;i++){
            if(num % i == 0){
                alert(num +'不是质数')
            }else{
                alert(num + '是质数')
            }
        }
```

