# react

## freeValue

```js
<Input freeValue={self.props.user} name="user" freeValueFilter={['number']} />
<Input freeValue={self.props.user} name="user" freeValueFilter={function (value) {
    return value.replace(/\D/g, '')
}} />
```


defaultValue 是一种外部缺省props的实现 (将指定 props 初次同步内部 state) 除了原生的 defaultValue 其实还有很多外部缺省 props 实现可以做。

外部缺省props都是对应 `onChange`的

freeValue 是在外部缺省 props 的实现之上允许外部 props 修改内部 state (这里的内部state对应上面的内部state)

freeValue 最直观的使用场景是，一个表单，即做编辑表单也做新增表单

freeValue 要有 reset 配合，且要支持 limit
reset 指的是这个功能 http://www.w3school.com.cn/jsref/met_form_reset.asp
