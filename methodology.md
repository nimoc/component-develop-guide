# methodology

编程（程序设计）将逻辑抽象成数据，通过触发事件改变数据。

例如点击按钮切换按钮颜色

```js
{
    btnColor: 'red'
}
// 点击按钮后
{
    btnColor: 'blue'
}
```

改变数据的过程包含逻辑判断，写出逻辑判断条件和条件对应的数据变动代码。


## 由单个问题中找出它的同类

> 参考 https://github.com/fast-flow/list-logic/issues/3  (翻页（单个问题） changePage(1)  翻页的同类search({page: 1}))

解决单个问题，代码适用性不强，且难以找到问题的本质。
