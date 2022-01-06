## User Status

```js

Bot.command('x', async ctx => {
    const chat_id = 123123213;
    const { status } = await ctx.api.getChatMember(chat_id, ctx.from.id);
    
    let isMember = status === 'member' || status == 'administrator'|| status==='creator';
    
    ctx.reply(isMember ? "You are a member" : "You are not a member");
})
```

## Only for admins
```js
Bot.on("message").filter(
  async (ctx) => {
    const user = await ctx.getAuthor();
    return user.status === "creator" || user.status === "administrator";
  },
  (ctx) => {
    const msg = ctx.message.text;
    if (msg === '/ban') {
      // ... do your task
    }
  },
);
```

## Question and Answer

```js
Bot.command("/start", ctx => {
  ctx.reply("Please enter your name");
}, 'name');

Bot.on("answer-name", ctx => {
  ctx.reply(`Hello, ${ctx.message.text}`);
})
```
