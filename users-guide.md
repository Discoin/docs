---
description: This guide contains frequently asked questions during Discoin transactions.
---

# User's Guide

{% hint style="warning" %}
**If you farm currencies,** specifically, if you operate a server exclusively for earning currencies for Discoin-participating bots, or we've found you intentionally spamming each bot to earn currencies, we'll notify all participating bot owners. **Violators will have their accounts deleted and permanently banned.**
{% endhint %}

## How can I exchange currency?

### Commands List

* `<Currency>` means 3-letter currency codes listed [here](https://dash.discoin.zws.im/#/currencies). Exchange rates are listed there too.

| Bot Name | Command | Note |
| :--- | :--- | :--- |
| [Dice\#6134](https://dice.js.org) | `$$convert-oats <Amount> <Currency>` | [Documentation](https://dice.js.org/commands/economy/convert-oats/) |
| [DiscordTel\#6675](https://discordtel.austinhuang.me) | `>convert <Amount> <Currency>` |  |
| [DueUtil 3.0\#0764](https://dueutil.xyz) | `!exchange <Amount> <Currency>` | Info: `!help exchange` |
| [Elite Looter\#8634](http://sjustein.com/html/elitelooter.html) | `;exchange <Amount> <Currency>` | Info: `;discoin` |
| [Gami\#7891](https://gami.app) | `-transfer <Amount> <Currency>` | Rates: `-transfer rates` |
| [KekBot\#2918](https://discordbots.org/bot/213151748855037953) | `$shop` then react 3 |  |
| [Murder Mystery Bot\#7898](https://top.gg/bot/319204121393496064) | `mm!convert <Currency> <Amount>` |  |
| [Pinocchio\#5540](https://pinocchiobot.xyz/) | `=exchange <Amount> <Currency>` | Info: `=discoin` |
| [Pollux\#9069](http://pollux.fun) | `+exchange <Amount> <Currency>` | `p!exchange` also |
| [Theelgirl's DueUtil\#6258](https://dueutil.org) | `!exchange <Amount> <Currency> <DUT/DUTC/DUP>` | Info: `!help exchange` |

## Can I get/spend Discoins?

No. Discoin only exists during the transaction process and statistics: As a universal _unit_ for calculating currency, it is only used for calculating exchange rates as well as currency reserves. The real world equivalent example would be [XDR](https://en.wikipedia.org/wiki/Special_drawing_rights).

## Can I have a transaction record?

[https://dash.discoin.zws.im/](https://dash.discoin.zws.im/)

## I did not receive my payment!

1. Check [the Transaction Record](https://dash.discoin.zws.im/). If it says the transaction isn't handled, the receiving bot hasn't processed it yet - By standard, bots should pick up its transactions on a 5-minute interval - so just wait patiently.
2. If it has been more than 5 minutes and the transaction still isn't handled, contact the developer\(s\) of the receiving bot.

## Suggested uses of each currency

Here's a table on the earning and spending mechanisms of each bot.

| Bot \(Currency Code\) | How to Earn \(Except voting\) | How to Spend |
| :--- | :--- | :--- |
| Dice \(OAT\) | `$$daily` and `$$dice-game` if won | Gambling in `$$dice-game` |
| DiscordTel \(DTS\) | `>daily` and `>lottery` if won | [Renewing your DiscordTel service](https://discordtel.austinhuang.me/en/latest/Payment/) as well as `>lottery` |
| DueUtil 3.0 \(DUTS\) | `!daily` as well as quests | `!shop` |
| Elite Looter \(ELT\) | Opening crates which can be gained by chatting and also `;games` | `;shop`ing upgrades as well as playing `;games` to get more crates |
| KekBot \(KEK\) | `$daily` and `$lottery` if won | `$shop`ing profile card decorations as well as playing `$slot` and `$lottery` |
| Gami \(GBC\) | `-daily`, `-beg`, `-steal`, `-work.` | `-gamble` |
| Murder Mystery Bot \(MMB\) | Typing `mm!globalgames` daily | `mm!globalgames` =&gt; Shop |
| Pinocchio \(PIC\) | `=dailies`, chat rewards, as well as coin drops if enabled | `=waifu` \(Buy discounted ones through `=rr`\) as well as `=paidroles` if set |
| Pollux \(RBN\) | `+daily`  | `+shop`ing crafting materials and profile decorations |
| Theelx's DueUtil \(DUT\) | `!daily`, `!joinjob` as well as quests | `!shop` for upgrades |
| ~ \(DUTC\) | `!daily` as well as quests | `!teamshop`  |
| ~ \(DUP\) | `!prestige` | `!prestigeshop` |

## Credits \(aka. "How can I support Discoin as a non-developer?"\)

* Discoin v3 is coded and hosted by [Jonah Snider](https://jonah.pw), owner of Dice. Consider supporting him on [Patreon](https://www.patreon.com/pizzafox) to help paying for server cost!
* The concept, math, and non-technical documentation of Discoin is developped by [Austin Huang](https://austinhuang.me), owner of DiscordTel. Considering [donating ](https://austinhuang.me/donate)as well!
* [Discoin is open source.](https://github.com/discoin/api-v3) If you cannot contribute financially, consider contributing your time reviewing the code!

