# encapsulation

> coming soon...

You need use `themes` encapsulation components.

```js
var Dialog = require('dialog.react').default
var NightDialog = React.createClass({
    render: function () {
        var themes = 'night ' + this.props.themes
        return (
            <Dialog {...this.props} themes={themes} />
        )
    }
})
module.exports = NightDialog
```
