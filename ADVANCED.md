## User Status
> This code will check the user status by using id.
```js

Bot.command('x', async ctx => {
    const chat_id = 123123213;
    const { status } = await ctx.api.getChatMember(chat_id, ctx.from.id);
    
    let isMember = status === 'member' || status == 'administrator'|| status==='creator';
    
    ctx.reply(isMember ? "You are a member" : "You are not a member");
})
```

## Only for admins
> This code will run only if the user is an admin.
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
> Ask questions a question and wait for an answer.
```js

Bot.command('start', ctx => {
  ctx.reply("First name");
  
  // add listener for fname
  ctx.question('fname')
});

Bot.on('answer', 'fname', ctx => {
  ctx.reply("Hello, " + ctx.from.first_name);
});

```

## Delete Forwaded Message
> Removes any message if it's forwaded from a channel. Bot must have permission to delete message.
```js
Bot.on(["channel_post", ":forward_date"], ctx => {
  ctx.deleteMessage()
})

```

