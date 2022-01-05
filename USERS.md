# By BotMate users

### 1. QR Code generator bot
[DOWNLOAD IMPORT FILE](https://t.me/BotMate/28939)

```js
// Pass true in the third parameter to make it a question
Bot.command("/start", ctx => {
  ctx.reply("Please send me your text to convert it to QR?");
}, 'qr');

// You can listen to the previous question using `on` event
Bot.on("answer-qr", ctx => {
  if (!ctx.message.text) {
    ctx.reply("Error. Retry with text. : /start")
    return
  }
  var txt = encodeURI(ctx.message.text)
  var srcLink = "https://chart.googleapis.com/chart?chs=150x150&cht=qr&chl=" + txt + "&choe=UTF-8"
  ctx.api.sendPhoto(ctx.from.id, srcLink, {
    caption: "QR for Text: " + ctx.message.text,
    reply_to_message_id: ctx.message.message_id
  })
})
```
