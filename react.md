# react

## freeValue

```js
<Input freeValue={self.props.user} name="user" freeValueFilter={['number']} />
<Input freeValue={self.props.user} name="user" freeValueFilter={function (value) {
    return value.replace(/\D/g, '')
}} />
```
