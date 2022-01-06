## Welcome New User
> Welcome your new user with a messagge

```js
Bot.on(":new_chat_members", (ctx) => {
    ctx.message.new_chat_members.map((user) => {
      ctx.reply(
        `Hi, <b>${user.first_name}</b>. Welcome to BotMate community group. ` +
          `Please read our <b>rules and guidelines</b> before you start using BotMate.\n` +
          `Talk good words, be safe.`,
        {
          reply_markup: new InlineKeyboard()
            .url("Rules", "https://docs.botmate.app/rules")
            .url("Docs", "https://docs.botmate.app")
            .row()
            .url("Testing Group", "https://t.me/+ZOhIYirxPTVFgbP3"),
          parse_mode: "HTML",
        }
      );
    });
  });
```
