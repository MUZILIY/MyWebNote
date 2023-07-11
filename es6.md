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
用于获取函数的实参，用来代替arguments
```
function date(...args)
{
    
}
date('a','b');
```

