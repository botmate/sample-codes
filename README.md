# Sample Code

Sample codes for BotMate Plaftorm

* [Basics](BASICS.md)
* [Formatting](FORMATTING.md)
* [Modules](MODULES.md)
* [Advanced](ADVANCED.md) <br>
* [By Users](https://github.com/botmate/sample-codes/blob/main/BY%20USERS.md)


### Simple Reply

```js
const handler = ctx => ctx.reply("Hello World");
Bot.command('start', handler);
```

### Reply with photo
```js
const handler = (ctx) => { 
  const link = "Photo Link"
  ctx.replyWithPhoto(`${link}`,{
    reply_to_message_id: ctx.msg.message_id,
  })
}

Bot.command('photo', hanlder);
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

Bot.command('start', handler);
```
 
