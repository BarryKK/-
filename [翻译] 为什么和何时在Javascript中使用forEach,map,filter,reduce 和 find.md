# 为何和何时在Javascript中使用forEach, map, filter, reduce 和 find。
[原文地址](https://medium.com/@JeffLombardJr/understanding-foreach-map-filter-and-find-in-javascript-f91da93b9f2c)

许多文章在讨论怎么在数组上使用`.forEach()`, `.map()`, `.filter()`, `.reduce()` 和 `.find()`。我认为解释何时使用这些通用的数组方法是很有的。

`.map()`, `.filter()`, `.reduce()` 和 `.find()` 与 `.forEach()` 的用法很相像，现在先让我们只关注后者。

### 什么是 `forEach`? 一种处理数组中元素的方法。

如果你对数组方法 `.forEach()` 不熟悉，每当你向遍历一个数组你可能会立即想到 `for` 循环。

`.forEach()` 只是一种不同的实现方法。下面两种代码实现了相同的事情。

`for` loop

```javascript
var array = [1,2,3];
for (var i = 0; i < array.length; i++){
  console.log(i);
}
```
`forEach()`

```javascript
var array = [1,2,3];
array.forEach(function(i){
  console.log(i);
});
```
这两种方法上微妙的不同可以对你的代码有巨大的影响。

### 为什么使用`forEach`? 简单易用

<font color=#FF0000> 对于我来说，最能让我使用 `forEach()` 来支持 `for` 循环的情景是它很简洁。 尽管他们有相同的代码行数，但是它需要的配置更少。</font> 使用寻常的 `for` 循环需要3步：

1. 定义一个迭代器值：var i = 0;
2. 定义一个结束点： i < array.length;
3. 告诉循环怎样迭代;

使用 `.forEach()` 你只需要简单的传入一个会被每个元素执行的方法。

### 为什么使用 `forEach`? 作用域
如果这些对你来说还不够的话... 使用`.forEach()` 支持 `for` 循环还有一个技术上的原因。他与代码的作用域有关。

当使用 `.forEach()` 时，传入了一个具有它自己作用域的函数。在 `for` 循环中，你正在污染循环中的作用域。大部分情况下（并非所有情况下），这是一个坏事。

### 何时使用 `forEach`?
`.forEach()` 你需要为每一个数组元素设置一个可执行的函数。好的情况时你应该使用 `.forEach()` 当你不能使用其他数组方法来实现你的目标。我知道这听起来很模糊，但 `.forEach()` 是一个通用的工具...当你不能使用更专业的工具处理数组时再使用它。

### 何时使用 `map` ?
`.map()` 当你想<big>**转换**</big>数组中的元素时

### 何时使用 `filter` ?
`.filter()` 当你想从一个数组中<big>**选出**</big>多个元素作为一个子集时。

### 何时使用 `find` ?
`.find()` 当你想从数组中<big>**选出**</big>一个元素时。

### 何时使用 `reduce` ?
`.reduce()` 当你想从一个数组中的多个元素中<big>**获得**</pig>一个值时。

### <font color=#FF0000>特性和批评</font>
#### `forEach` 返回 undefined
如果你希望转换整个数组，你可能会想使用 `.map()`。`.map()`返回一个数组是有用的，因为链接其他数组方法。

Example:
```javascript
const arr = [1,2,3];
const transformedArr = arr.map(function(){}).filter(function(){});
```
<font color=#FF0000>关于性能的一些话</font>
一个最大的**批评**就是 `.forEach()` 的运算速度。

在现实中，你不应该使用 `.forEach()` 除非其他方法像 `.map()`不能完成需求。 `.map()` 事实上在速度上要略快于 `.forEach()`。

坦白的讲，`.forEach()` 和 `.map()` 要慢于原生的 `for` 循环。但仅仅根据执行速度的快慢去判断是否使用这个方法是目光短浅的。这个观点完全忽略了代码的易读性和作用域。

这里的关键点是你不使用 `for` 循环因为你认为它们更快，使用它们当你知道你需要的时候。
