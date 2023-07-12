# ajax
https://blog.csdn.net/weixin_44972008/article/details/113772348

https://github.com/Nliver/AJAX-Study

## 发送
```
const xhr=new XMLHttpRequest();
xhr.open('GET','http://');
xhr.send()
xhr.onreadystatechange = function(){

}
```

## axios
### 语法
```
1.引入axios:https://cdn.jsdeliver.net/npm/axios/dist/axios.min.js
2.使用axios函数
axios({
    url：'目标资源地址'
}).then((result)=>{

})
```


# es6
## let
1. 变量不能重复声明
2. 块级作用域，外面不能用里面的
3. 不存在变量提升
4. 不影响作用域链
## const
1. 一定要赋初值
2.  常量的值不能修改
3. 块级作用域
4. 一般常量用大写
5. 对数组和对象的元素进行修改，不算做对常量的修改，不会报错
## 模板字符串
```
`&{变量}`
```
## 对象的简化写法
```
let name='a'
let age = 18

cnost obj={
    name,
    age,
    sayhi(){
        console.log('hi);
    }
}
```

## 箭头函数
```
let fn = function(){

}

let fn = () =>{

}
```
**this是静态的**，始终指向函数声明时所在作用域下的this的值，即箭头函数this的值=上一级作用域的this值
**不能做为构造函数实例化对象**
不能使用arguments变量
简写：省略小括号 or 省略大括号
## rest参数
放到最后
用于获取函数的实参，用来代替arguments
```
function date(...args)
{
    
}
date('a','b');
```
## 扩展运算符
```
[]...]
应用：数组的合并、克隆（浅拷贝）、将伪数组转为真正的数组
```
## Symbol
表示独一无二的值，类似于字符串的数据类型
```
let s = Symbol()
```
特点：
1. 值是唯一的
2. 值不能与其他数据进行运算
3. 定义的对象属性不能使用for…in循环，但是可以使用Reflect.ownKeys来获取对象的所有键名

## 迭代器
```
for in ：输出索引值，可以遍历原型链上面的属性
for of：输出值
```
工作原理：
1. 创建一个指针对象，指向当前数据结构的起始位置
2. 第一次调用对象的next方法，指针自动指向数据结构的第一个成员
3. 接下来不断调用next方法，指针一直往后移动，直到指向最后一个成员
4. 每调用next方法返回一个包含value和down属性的对象

## 生成器
