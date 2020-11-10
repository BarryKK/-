# 为什么和何时在Javascript中使用forEach,map,filter,reduce 和 find

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


