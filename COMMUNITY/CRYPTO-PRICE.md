```js
Bot.command('p',async ctx => {
    let input = ctx.message.text
    let s = input.split(" ")[1];
    let res = await Http.get(`https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&symbols=${s}`);
    let message =`
           #️⃣ RANK     : ${res.data[0].market_cap_rank}
      #️⃣ NAME     : ${res.data[0].name} 
      💲 PRICE    : ${res.data[0].current_price} $
      🚀 ATH      : ${res.data[0].ath} $
      📅 ATH DATE : ${res.data[0].ath_date}

      🟢 24L   = ${res.data[0].low_24h}$
      🟢 24H  = ${res.data[0].high_24h}$
      🔴 price change 24h  = ${res.data[0].price_change_percentage_24h}%


      💁‍♂️ TOTAL SUPPLY     : ${res.data[0].total_supply}
      ⏳ TOTAL VOLUME : ${res.data[0].total_volume}
      🎓 MAeKET CAP : ${res.data[0].max_supply}
    ` ;
    ctx.reply(message)
})
```

By @Radical_11111
