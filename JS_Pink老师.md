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
### 箭头函数ss
#### 