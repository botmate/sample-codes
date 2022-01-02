## Listen to all commands

```js
const handler = (ctx) => {
  ctx.reply(`You've send ${ctx.message.text}`);
}

module.exports = {
  command: /.*/,
  handler
}
```
