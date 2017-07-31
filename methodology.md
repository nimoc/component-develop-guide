# methodology

> **目前 methodology 还在撰写状态，只记录方法，不做详细解释**

## 数据快照

编程（程序设计）将**逻辑**抽象成**数据**，通过**触发事件改变数据**。

例如点击按钮切换按钮颜色

```js
// 初始
{
    btnColor: 'red'
}
// 点击按钮后
{
    btnColor: 'blue'
}
// 再次点击
{
    btnColor: 'red'
}
```

改变数据的过程包含逻辑判断，写出逻辑判断条件和条件对应的数据变动代码。

> 基于 `React/Vue` 的组件实现天然是数据快照的实现（声明式），但某些逻辑封装的库也可以使用数据快照的方式做前期的分析设计。

## 由单个问题中找出它的同类

> 参考 https://github.com/fast-flow/list-logic/issues/3  (翻页（单个问题） `changePage(1)`  翻页的同类 `search({page: 1}))`

解决单个问题，代码适用性不强，且难以找到问题的本质。

找到将多个同类需求用同一个接口实现，逻辑更合理清晰。

## 解耦-减少内部函数

> 解耦，减少依赖。

尽量避免内部函数。虽然定义内部函数后可以不传参直接获取当前函数作用域的所有值，但是会让代码耦合度高。内部函数不可在其他函数中复用。

若独立出一个没有任何依赖的函数，且通过传参的方式传递数据，并明确返回修改后的数据。代码更易于阅读和管理。*传参超过 2 个则使用  `fn({...})` 形式而不是 `fn(a, b ,c ,d ,e)` 这种难以阅读的形式 *

好的例子：
```js
function test(value, rule) {
    return rule.map(function (item) {
        return checkItem(value, item)
    })
}
function checkItem(value, item) {
    var output = {}
    if (item.regexp.test(value) !== item.be) {
        output.error = true
        output.msg = item.msg
    }
    else {
        output.error = false
    }
    return output
}
test(
    'abc',
    [
        {
            regexp: /\d/,
            be: true,
            msg: '必须包含数字'
        }
    ]
)
```
