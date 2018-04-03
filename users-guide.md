# Discoin Guide for Users

This guide contains frequently asked questions during Discoin transactions.

## How can I exchange currency?

Before you can exchange currency, you must [verify yourself](http://discoin.sidetrip.xyz/verify). After verification, refer to the table below.

### Commands List

* `<Currency>` means 3-letter currency codes listed [here](http://discoin.sidetrip.xyz/rates). Exchange rates are listed there too.

| Bot Name                                                             | Command                              | Note                                                                        |
|----------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------|
| [Dice#6134](https://dicediscord.netlify.com/)                        | `$$convert-oats <Amount> <Currency>` | [Documentation](https://dicediscord.netlify.com/discoin) |
| [DiscordTel#6675](http://discordtel.rtfd.io)                         | `>convert <Amount> <Currency>`       |                                                                             |
| [Elite Looter#8634](https://bots.discord.pw/bots/303799630532050946) | `;exchange <Amount> <Currency>`      | Info: `;discoin`                                                            |
| [KekBot#2918](https://discordbots.org/bot/213151748855037953)        | `$shop convert`                      |                                                                             |
| [Pollux#9069](http://pollux.fun)                                     | `+exchange <Amount> <Currency>`      | `p!exchange` also                             |

## Why do I need to give out my email?

To prevent users bypassing daily limits by making multiple accounts, we use your email address to filter some of them out. **We do not record or store your email address**, [as indicated in the source code](https://github.com/MacDue/DiscoinRewrite/blob/master/discoin/users.php#L147).

## Can I spend Discoins?

No. Discoin only exists during the transaction process and statistics: As a temporary currency, Discoin can only be converted from one currency to another; as a universal *unit* for calculating currency, it is only used for calculating exchange rates.

## Can I have a transaction record?

[Yes.](http://discoin.sidetrip.xyz/record)

## Why are there transaction limits?

While some bots have interesting features, they are vulnerable once the "challenge" in it has disappeared: For example, if you are playing RPG on a bot, one of your goals would be earning money to improve yourself. Discoin is supposed to be a tool helping you to reach that goal, not *a hack reaching the goal directly for you*. Without transaction limit, you will lose the power to continuing playing RPG on the bot. Also, a bot's currency system is vulnerble to inflations.

For this reason, we allow bot owners to implant transaction limits for their currencies. There are two types of limits:

### Daily per-User Limit (DUL)

It's how much a user can exchange from any other currency to a specific currency in a day. By default, the limit is 5000. Your remaining limit is sent back to the bot when you submit a transaction.

### Daily Total Limit (DTL)

It's how much all users can exchange from any other currency to a specific currency in a day. Currently, only DueUtil has a limit of 100,000 Discoins per day. The remaining limit is not sent back to the bot.

### What if I exceeded the limit?

We'll decline the transaction.

## I did not receive my payment!

1. Check [the Transaction Record](http://discoin.sidetrip.xyz/record). If it says "Unprocessed" on "Reception Date", the receiving bot hasn't pick up its unprocessed transactions yet - By standard, bots should pick up its transactions on a 5-minute interval - so just wait patiently.
2. If it has been more than 5 minutes and the status remains "Unprocessed", contact the developer(s) of the receiving bot. Alternatively, type other commands of the bot to ensure it is working properly.
3. If a timestamp is present on "Reception Date", please go to [our support server](https://discord.gg/NExXSDH) and submit a dispute.

## Suggested uses of each currency

Here's a table on the earning and spending mechanisms of each bot.

| Bot (Currency Code) | How to Earn | How to Spend |
| ------------------- | ----------- | ------------ |
| Dice (OAT) | `$$daily` and `$$dice-game` if won | Wager in `$$dice-game` |
| DiscordTel (DTS) | `>daily` and `>lottery` if won | [Renewing your DiscordTel service](https://discordtel.austinhuang.me/en/latest/Payment/) as well as `>lottery` |
| Elite Looter (ELT) | Opening crates which can be gained by chatting and also `;games` | `;shop`ing upgrades as well as playing `;games` to get more crates |
| KekBot (KEK) | `$daily` and `$lottery` if won | `$shop`ing profile card decorations as well as playing `$slot` and `$lottery` |
| Pollux (RBN) | `+daily` and `+pick` up someone's dropped Rubines | `+drop` to let someone pick up your Rubines as well as `+shop`ing crafting materials and profile decorations |
