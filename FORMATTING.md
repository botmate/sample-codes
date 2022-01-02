## Send in bold

```js
const handler = (ctx) => {
  ctx.reply("*I am bold*", {
    parse_mode: "Markdown"
  });
}

module.exports = {
  command: '/start',
  handler
}
```

## Send in Italic

```js
const handler = (ctx) => {
  ctx.reply("_I am bold_", {
    parse_mode: "Markdown"
  });
}

module.exports = {
  command: '/start',
  handler
}
```

## HTML Formatting

```js
const handler = (ctx) => {
  ctx.reply('<b>Hi!</b>, Learn more at <a href="https://docs.botmate.app">BotMate Docs</a>.", {
    parse_mode: "Html"
  });
}

module.exports = {
  command: '/start',
  handler
}
```
