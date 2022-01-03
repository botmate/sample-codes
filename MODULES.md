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

## All command handler

```js
Bot.command(/.*/, ctx => {
  const msg = ctx.message.text;
  switch(msg) {
     case '/start':
        ctx.reply("Welcome");
        break;
     case '/help':
        ctx.reply("No help haha");
        break;
     case '/about':
        ctx.reply("About me");
        break;
     default:
        ctx.reply("No command found");    
  }
});
```
