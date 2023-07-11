 # JS_Pink老师
# JS_B站pink老师
## 事件委托
### 原理
事件冒泡
阻止事件冒泡 e.stopPropagation()
链接的跳转，表单域跳转e.preventDefault()
### 好处
1. 很多子盒子要绑定相同的事件，只需要在他们的父盒子上绑定一次就行
2. 利用事件流的特征解决一些开发需求
    1. 减少注册次数，可以提高程序性能
### 实现
事件对象e.target.tarName获取真正触发事件的元素

## 自定义属性
```
<div data-id="0"> </div>

<script>
const div = doucument.querySelector("div");
console.log(div.dataset.id)//0
</script>
```

## 正则表达式
测试是否匹配 
**正则表达式.test(被检测地方字符串)**
返回 true 或者 false

检索符合规则的字符串
**正则表达式.exec(字符串)**
返回数组

### 元字符 
#### 边界符  
**^ 
$**
如果^和$同时出现，代表精确匹配

#### 量词
```
*：出现0~多次
+：出现1~多次
？：出现0或1次
{n}：出现n次
{n,}：出现n到多次
{n,m}：出现n到m次
```
#### 字符类
[]匹配字符集合，括号里面只选一个
[]{2}括号里面可以有两个
```
.：除了\n以外的任意字符
[^]  ^写在括号里面代表取反
```

#### 预定义类
```
\d：匹配数字0~9
\D: 匹配非数字0~9
\w：匹配字母、数字、下划线
\W: 匹配所有数字、字母、下划线以外的字符
\s: 匹配空格
\S: 匹配非空格
```

#### 修饰符
```
/i: 匹配不区分大小写
/g：全局匹配
```

## 页面事件
### 页面滚动
scroll;
scrolltop   /   scrollleft
scrollto
### 页面尺寸
浏览器页面尺寸改变时触发
resize
clientWidth  /  clientHeight (可见部分的宽高，
含padding；不含边框、margin、滚动条)
元素大小及其相对视口的位置：element.getBoundingClientRect();
![Img](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230523100342.png)
offsetWidth/offsetHeight：内容+padding+border

## 做tab的方法
1. offset + transform
2. for 循环 + ${i+1 }

## DOM节点相关操作
### 查找DOM节点
| 查找xx节点 | 属性 |
| -- | -- |
| 查找父节点 | parentNode |
| 查找子节点 | children |
|  查找兄弟节点 | nextElementSibling <br> previousElementSibling |

### 增加节点
子元素插入到父元素的最后：父元素.appendChild(要插入的元素)
子元素插入到父元素前面：父元素.insertBefore(要插入的元素，在哪个元素前面)
### 克隆节点 
cloneNode()
### 删除节点
父元素.removeChild(要删除的元素)

## M端(移动端)事件
|触屏事件|说明|
|--|--|
|touchstart| 触摸DOM元素时触发 |
|touchmove| 在DOM元素上滑动时触发|
|touchend| 在DOM元素上离开时触发|

## BOM（浏览器对象模型）
windows是JavaScript中最大的、顶级的对象

## 定时器
### 间歇函数setInteval(回调函数，等待的ms)
每隔一段时间执行一次，除非手动清除
### 延时函数setTimeout(回调函数，等待的ms)
执行一次
清除：clearTimeout(延时函数名)

## 本地存储
### location
#### 倒计时结束后自动跳转
#### href属性：利用href赋值的方法跳转页面
#### seach属性
获取地址中携带的参数，符号？后面的部分
哈希值是#后面的部分

### navigator
![Img](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230701112214.png)

存储数据 : localStorage.setItem(key,value);
取数据 : localStorage.getItem(key);
### 存**复杂**数据类型
1. 需要将复杂数据类型转换成**JSON字符串**(属性和值都有引号，且都是双引号))，载存储到本地
eg:JSON.stringify()
2. 把JSON字符串转换为对象
JSON.parse(localStorage.getItem('obj));

__数据存储是先先转换再存储<br>得到数据是先得到再转换<br>删除数据是先得到再删除__

## 字符串拼接
map()  join()
### map()
遍历数组，并且返回新数组
### join()
把数组中的字符连接起来为一个字符串

## 创建对象的方法
1. 利用对象字面量创建对象
```
const obj={}
```
2. 利用new Object创建对象
```
const obj = new Object({uname:'a'})
```
3. 构造函数  **大写字母开头**
### 构造函数
创建多个类似的对象
new关键字调用函数的行为——实例化
构造函数内部不需要写return，返回自动创建的对象
```
function Pig(name,age)
{
    this.name=name;
    this.age=age;
}
const Peppa=new Pig('peiqi',6);
```

#### 过程
1. 创建新的空对象
2. 构造函数this指向新对象
3. 执行构造函数代码，修改this，添加新属性
4. 返回新对象
#### 实例成员和静态成员
实例成员：实例对象的属性和方法;实例对象相互独立
静态成员：构造函数的属性和方法
#### 静态方法
```
const arr={name:"pink",age:18}
const obj={}
1.  arr.keys() //获取属性名  name age
    arr.values()  //获取属性值  pink 18
2.  Object.assign(obj,arr) //把arr对象拷贝给obj  {}
  //Object.assign(arr,{gender："man"}) 还可进行对象属性的添加

```
## 数组的方法
**foreach()**:不返回新数组，遍历
**filter()**:过滤，返回满足条件的数组
**map()**:返回新数组
**reduce()**:返回 和
**join()**:拼接为字符串，返回字符串
**find()**:查找第一个符合条件的元素值，没有则返回undefined
**every()**:检测数组中所有元素都符合指定条件，是返回true，不是返回false
**some()**:数组中是否有满足条件的元素，是返回true
**sort()**:原数组排序
**concat()**:返回合并后的新数组
**splice()**:删除或替换原数组单元
**reverse()**:反转数组
**findIndex()**：查找元素的索引值

## 字符串的方法
**length()**:获取长度
**substring()**:字符串拆分为数组
**substring()**:字符串截取
**startWith()**:检测是否以某字符开头
**endWith()**:检测是否以某个字符结尾
**includes()**:判断一个字符串是否包含在另一个字符串中，返回true/false
**toUpperCase()**:转换为大写
**toLowerCase()**:转换为小写
**indexOf()**:检测是否包含某个字符
**replace()**:替换字符串
**match()**:查找字符串
**split(以什么分割)**:将一长串字符串以()中的符号进行分割，返回分割后的数组

## js高级
### 作用域
1. 局部作用域
    a)函数作用域
    b)块作用域
2. 作用域链的本质是变量查找机制

### 垃圾回收机制
生命周期：内存分配、使用、回收
一般，全局变量不会回收，局部变量在不使用后会自动回收
栈中存放基本数据类型，操作系统自动分配释放
堆中存放对象，里面的数据，需要程序员分配
#### 两种常见算法
##### 引用计数法
##### 标记清除法（现在一般用）
### 闭包
内层函数访问外层函数的作用域
**闭包=内层函数+外层函数的变量**
作用：封闭数据，提供操作；外部也可以访问内部的变量
可能引起**内存泄漏**
### 函数参数
#### 动态参数
**arguments**：本质是伪数组、
eg：求和时传入参数个数不定
箭头函数没有
#### 剩余参数：本质是数组，将不定数量的参数表示为一个数组（一般用这个）
```
(a,b,...arr)
```
#### 展开运算符
写在函数外面
(...arr)，将一个数组展开
eg：求数组最大值、最小值；
```
const arr[1,2,3]
console.log(Math.max(...arr)) //3
```
合并数组
```
const arr1=[1,2,3];
const arr2=[4,5,6];
console.log([...arr1,...arr2]);  ///1,2,3,4,5,6
```
### 箭头函数
```
const fn = (参数) => {
    代码
}
```
只有一个参数时，可以省略小括号
只有一行代码时，可以省略大括号和return
直接返回对象，需要加小括号 ({对象})
#### this
谁调用指向谁
不会创建自己的this，只会从作用域的上一层沿用this，相当于上一层指向的this

### 解构赋值
#### 数组解构：将数组的单元值快速批量赋值给一系列变量的简洁语法
```
    const arr=[100,80];
    const [max,min]=arr;
    console.log(max,min);  //100 80
```
两种必须加分号的情况：
1. 立即执行函数
2. 数组解构

#### 对象解构
解构属性和方法
```
    const obj={
        uname:'pink',
        age:18
    }
    const {uname,age} =obj;  //变量名要和属性名相同
    console.log(uname,age);

    //改名，旧变量名：新变量名
    const {uname：username,age} =obj; 
```
```
    //多级对象解构
    const pig={
        name:'peiqi',
        family:{
            mother:'mama',
            father:'baba',
        },
        age:5
    }
    const {name,family:{mother,father},age}=pig
    console.log(name,age,mother); //peiqi 5 mama
```

### foreach()遍历数组
数组.foreach(function(当前数组元素,元素索引号)){
    //函数体
}
类似map，但只遍历，不返回数组
索引号可不选

### 面向对象编程
#### 特性：
封装性：构造函数
继承性：
多态性：
#### 优点
易维护、易复用、易扩展；更加灵活
缺点：性能比面向过程低

### 原型
![Img](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230707141925.png)

#### constructor()
构造函数的一个属性prototype()指向原型，原型也是一个对象；原型对象中的一个属性constructor()指回构造函数
eg:star.prototype.constructor === star //true

如果是直接给原型对象的prototype()赋值的话，相当于prototype()里面的值被替换了，constructor()属性没有了，找不到父亲了，所有需要加上constructor的指向
![Img](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230707154941.png)

![Img](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230707155118.png)

#### 原型对象和对象yuanx
原型对象：构造函数的prototype属性
对象原型：实例对象上的__proto__属性，有时候也表示为[[prototype]]

关系图
![关系图](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230707170040.png)

#### 原型继承
1. 通过原型链继承
![原型链继承](https://raw.githubusercontent.com/MUZILIY/blog-imgs/main/imgs/yank-note-picgo-img-20230708094349.png)
2.只要是对象，就有__proto__
只要是原型对象，就有constructor
3. intanceof() :查找是否在原型链上

### 拷贝：只针对引用类型
#### 深拷贝：
拷贝的是对象
eg：通过递归实现、lodash/cloneDeep、通过JSON.stringify()实现
#### 浅拷贝：
拷贝对象后，如果里面的属性值是简单数据类型就直接拷贝值
如果属性值是引用数据类型则拷贝地址
eg：拷贝对象、数组
```
const o ={...obj}
```
**直接赋值和浅拷贝的区别**：
1.直接赋值：只要是对象，就会相互影响，因为是直接拷贝对象栈里面的地址
2. 浅拷贝如果是一层对象，不相互影响，如果出现多层对象拷贝还会相互影响
 
### 异常处理
#### throw抛异常
```
    throw 'no canshu'
    throw new Error('no canshu')
```

#### try/catch捕捉异常
try:可能发生错误的代码
catch：拦截写错了的代码。只拦截错误，提示浏览器提供的错误信息，但不会中断程序，加return中断
finally：不管代码对不对，一定会执行的代码
```
function fn()
    {
        try{
            const p=document.querySelector('.p')
            p.style.color='red'
        }catch(err){
            console.log(err.message);
            return;//中断
        }
        finally{
            // alert('alert')
            console.log(11);
        }
    }
```

#### debuger
调试

### this
#### 普通函数：谁调用指向谁
箭头函数：函数内不存在this，沿用上一级的；不适用于构造函数、原型函数、dom事件函数

#### 改变this指向
##### call()
```
fun.call(函数运行时指定的this,传递的其他参数)
fun.call(obj,avg1,avg2)
```
返回函数的返回值
手撕源码
```
Function.prototype.myCall()=function(ctx,...args)
    {
        ctx=(ctx===null||ctx===undefined)?globalThis:Object(ctx);
        var key=Symbol('temp');
        Object.defineProperty(ctx,key,{
            enumerable:false,
            value:this,
        });
        var result = ctx[key](...args);
        delete ctx.fn;
        return result;
   }
```

##### apply()
```
fun.apply(obj,[avgs])
```
传递的值必须包含在数组里面
使用场景：求数组最大值
```
const max = Math.max.apply(Math,[1,2,3]);
```
##### bind()
不会调用函数，但能改变函数内部的this指向
```
fun.bind(thisarg,arg1,arg2,……)
```

### 防抖和节流
#### 防抖
单位时间内，频繁触发事件，只执行**最后一次**
使用场景：搜索框输入、手机号，邮箱验证输入
##### 实现方式：
1. lodash提供的防抖来处理（常用）
```
<script src="https://cdn.bootcdn.net/ajax/libs/lodash.js/4.17.21/lodash.js"></script>

_.debounce(func,[wait=0],[options=])
```
2. 手写一个防抖函数来处理
核心思路是：利用定时器实现
```
const box = document.querySelector('.box');
let i =1;
function mouseMove()
{
    box.innerHTML=i++;
    //如果里面存在大量消耗性能的代码，比如dom操作、数据处理，可能造成卡顿
}
function mydebounce(fn,t)
{
    //1.声明定时器变量
    let timer;
    //返回一个匿名函数,因为mydebounce函数带了小括号，相当于调用函数，所以直接写，一打开就会执行完，不会再次使用；而我们需要每次鼠标滑动就执行一次
    return function(){
        //2.每次鼠标移动(触发事件)的时候都要先判断是否有定时器，如果有就县清除以前的定时器
        if(timer) clearTimeout(timer);
        //3.如果没有定时器，则开启定时器，存入到定时器变量里面
        timer=setTimeout( function(){
            //4.定时器里面写函数调用
            fn()//加小括号调用函数
        }, t);
    }
}
box.addEventListener('mousemove',_.debounce(mouseMove,500))
```
#### 节流
单位时间内，频繁触发事件，只执行第一次，防止多次提交
使用场景：高频事件：鼠标移动、页面尺寸缩放、滚动条滚动
##### 实现方法
1. lodash提供的节流函数来处理（常用）
```
video.ontimeupdate=_.throttle(()=>{},1000)
```

2. 手写一个节流函数`
核心思想：定时器setTimeout
```
1. 声明一个定时器变量
2.当鼠标每次滑动都先判断是否有定时器了，如果有定时器则不开启新的
3. 如果没有则开启定时器，存到变量里
3.1 定时器里面调用执行的函数
3.2 定时器里面要把定时器清空
```
#### 案例：页面打开，可以记录上一次的视频播放位置
思路：
1. 在ontimeupdate事件触发的时候，每隔1s，就记录当前时间到本地存储
2. 下次打开页面，onloadeddata事件触发，就可以从本地存储取出时间，让视频从取出的时间播放，如果没有就默认为0s
3. 获得当前时间video.currentTime3

