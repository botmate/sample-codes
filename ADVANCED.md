## Check if user is a member of a chat

```js

Bot.command('x', async ctx => {
    const chat_id = 123123213;
    const { status } = await ctx.api.getChatMember(chat_id, ctx.from.id);
    
    let isMember = status === 'member' || status == 'administrator'|| status==='creator';
    
    ctx.reply(isMember ? "You are a member" : "You are not a member");
})
```

## Questin and Answer

```js
Bot.command("/start", ctx => {
  ctx.reply("Please enter your name");
}, true);

Bot.on("answer", ctx => {
  ctx.reply(`Hello, ${ctx.message.text}`);
})
```
