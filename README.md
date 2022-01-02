# Sample Code

Sample codes for BotMate Plaftorm


### Simple Reply

```js
module.exports = {
  command: '/start',
  handler: ctx => ctx.reply("Hello World");
}
```

### Reply with photo
```js
const handler = (ctx) => { 
const link = "Photo Link"
ctx.replyWithPhoto(`${link}`,{
reply_to_message_id: ctx.msg.message_id,
})
}

module.exports = {
  command: 'commandName',
  handler,
}
```

### URL Inline Keyboard
```js
const inlineKeyboard = new InlineKeyboard().url(
  "BotMate Documentation",
  "https://docs.botmate.app",
)

const handler = (ctx) => {
  ctx.reply("Worked", {
    reply_markup: inlineKeyboard,
  });
}

module.exports = {
  command: '/start',
  handler
}
```
