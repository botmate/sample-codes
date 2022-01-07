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

## Ban senderChat
> Bans channel messages from users, along with logs. [You can also Download importable File](https://t.me/BotMate/33515)
```js
Bot.hears(/.*/, ctx => {
  if (ctx.message.sender_chat) {
    //Bot must be admin in logs channel
    //Logs channel:
    var logs = "@chatblocksLogs"
    ctx.api.sendMessage(logs, "Banned: @" + ctx.message.sender_chat.username)
    var id = ctx.message.sender_chat.id
    //ctx.api.deleteMessage("@botsTestbyKp", ctx.message.message_id)
    //Bot must be Admin in chat with ban user permissions 
    //Block code:
    ctx.api.banChatSenderChat("@botsTestbyKp", id)
  }
})
```

