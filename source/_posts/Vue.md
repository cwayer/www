# Vue

## 1 vue简介

Vue (读音 /vju/，类似于 **view**) 是一套用于构建用户界面的**渐进式框架**。和AngularJS的语法非常的相似。

Vue 的一些语法和 AngularJS 的很相似 (例如 `v-if` vs `ng-if`)。因为 AngularJS 是 Vue 早期开发的灵感来源。然而，AngularJS 中存在的许多问题，在 Vue 中已经得到解决。

### 1.1 MVVM模式

MVVM模式： 

M ： Model  (数据)

V  ：View（视图）--静态页面

VM ：vue 的实例 

![1541917907117]](https://raw.githubusercontent.com/cwayer/assets/master/1541917907117.png)

```js
const vm = new Vue({
      // this  ---》 当前的 VM的实例
    el:"#id",   // id任意即可
    data:{
        message:"hello..."
    }
})
```

## 2 Vue常用的指令

### 2.1 插值表达式

```js
{{  message }}   // 表达式内可以 写算术运算， 调用vue的方法， 但是不可以定义 js的变量等

```

### 2.2 v-on

**v-on:**click ,  v-on:keydown   和原生js 一样的，vue给我们提供简写的方式  **@click**, 绑定事件的处理

### 2.3 v-text 和 v-html 和 v-bind

v-text: 绑定的数据是文本

v-html: 显示带HTML代码的数据， 也可以显示存文本

v-bind:  **强制**绑定HTML标签的属性上， 简写： 如：v-bind:href="url"   ， 简写 :href="url"

	简写:

### 2.4 v-model

绑定表单中得HTML的变量

你可以用 `v-model` 指令在表单 `<input>`、`<textarea>` 及 `<select>` 元素上创建双向数据绑定。它会根据控件类型自动选取正确的方法来更新元素。尽管有些神奇，但 `v-model` 本质上不过是语法糖。它负责监听用户的输入事件以更新数据，并对一些极端场景进行一些特殊处理。

![1541918549542]](https://raw.githubusercontent.com/cwayer/assets/master/1541918549542.png)

### 2.5 v-for

v-for： 循环遍历 ，  字符串数组， 遍历对象， 集合...

es6中要加冒号后面写唯一值即可

```js
v-for="(item, index) in list "  :key="index"
```

### 2.6 v-if 和 v-show

判断是否显示当前的变量的值， 如果条件成立，显示， 否则不显示

![1541919561891]](https://raw.githubusercontent.com/cwayer/assets/master/1541919561891.png)

## 3 Vue生命周期

![1541921551752]](https://raw.githubusercontent.com/cwayer/assets/master/1541921551752.png)

![1541921578169]](https://raw.githubusercontent.com/cwayer/assets/master/1541921578169.png)

8个分为三大类：

1. 初始化方法（四个）只会调用一次
2. 更新显示（循环）
3. 销毁VM实例

## 4 axios异步调用

[参考官网](https://github.com/axios/axios)



