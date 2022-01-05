# Sample Code

Sample codes for BotMate Plaftorm

* [Basics](BASICS.md)
* [Formatting](FORMATTING.md)
* [Modules](MODULES.md)
* [Advanced](ADVANCED.md) <br>
* [By Users](https://github.com/botmate/sample-codes/blob/main/BY%20USERS.md)


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

### Editing inlineKeyboard when pressed
```js
const inlineKeyboard = new InlineKeyboard()
  .text("Button text", "Events");

 const handler = (ctx) => {
  ctx.reply("Worked.", {
    reply_markup: inlineKeyboard,
  });
}

module.exports = {
    command: 'Command Name',
    handler,
    callback: {
      event: "Events",
      handler: ctx => {
        ctx.editMessageText(
          "Your new Text here", {
            //Can change Your keyboard:
            reply_markup: inlineKeyboard,
          }
        }
      }
    }
```
