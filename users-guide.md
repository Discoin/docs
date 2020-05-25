---
description: This guide contains frequently asked questions during Discoin transactions.
---

# User's Guide

{% hint style="info" %}
Discoin is meant to supplement user income on each bot. While certain actions, like  investments, are encouraged by design, everything has a limit. To keep the economies running in reasonable order, please convert currencies reasonably and responsibly.
{% endhint %}

{% hint style="danger" %}
**The following actions are prohibited on Discoin. Violators will be punished at the discretion of each participating bot owners.**

* Converting any currency, illicitly acquired, within the Discoin system. By "illicitly acquired", actions include, but are not limited to, the following:
  * Automated actions, including macros, selfbotting, etc.;
  * Exploitations of bot mechanisms in any way not intended by bot owners;
  * Acquisitions of currency that are illicitly acquired by other users;
  * Other actions prohibited by terms and conditions imposed by other parties, including but not limited to participating bots and Discord.
* Perform automated transactions, through macros, selfbotting, etc.
* Exploit Discoin mechanisms in any way not intended by developers \(e.g. pump & dump\).
* Any action that can fall under "Unlawful Access of Computers".
{% endhint %}

## How can I exchange currency?

### Procedure

1. Create a transaction from the origin bot. See the command list below.
2. Your transaction will be converted at the rates effective at the moment. After a transaction, the rates will [adjust itself](untitled.md).
3. Within 5 minutes, the destination bot will receive your transaction. [Unless...?](users-guide.md#i-did-not-receive-my-payment)

### Commands List

* `<Currency>` means 3-letter currency codes listed [here](https://dash.discoin.zws.im/#/currencies). Exchange rates are listed there too.

| Bot Name | Command | Note |
| :--- | :--- | :--- |
| [BattleBanana\#0764](https://dueutil.xyz) | `!exchange <Amount> <Currency>` | Max 500k BBT per transaction |
| [ChaosRPG\#3409](https://top.gg/bot/603974948335124491) | `?convert <Amount> <CURRENCY>` | Rates: `?rates`. Must create account:`?start` |
| [Dice\#6134](https://dice.js.org) | `$$convert-oats <Amount> <Currency>` | Rates: `$$discoin-rates` |
| [Digimon Universe\#9783](https://top.gg/bot/617159282668077066) | `d-exchange <Currency> <Amount>` |  |
| [DiscordTel\#6675](https://discordtel.austinhuang.me) | `>convert <Amount> <Currency>` |  |
| [DueUtil 3.0\#0764](https://dueutil.xyz) | `d!exchange <Amount> <Currency>` | Max 500k DUC per transaction |
| [Elite Looter\#8634](http://sjustein.com/html/elitelooter.html) | `;exchange <Amount> <Currency>` | Info: `;discoin` |
| [Gami\#7891](https://gami.app) | `-transfer <Amount> <Currency>` | Rates: `-transfer rates` |
| [KekBot\#2918](https://discordbots.org/bot/213151748855037953) | `$shop` then react 3 |  |
| [Lootcord\#6294](https://lootcord.com) | `t-convert <Amount> <Currency>` |  |
| [Murder Mystery Bot\#7898](https://top.gg/bot/319204121393496064) | `mm!convert <Currency> <Amount>` | Must create account:`mm!globalgames` |
| [Nova\#2243](https://top.gg/bot/460952742672990217) | _coming soon_ |  |
| [Pinocchio\#5540](https://pinocchiobot.xyz/) | `=exchange <Amount> <Currency>` | Info: `=discoin` |
| [Pollux\#9069](http://pollux.fun) | `+exchange <Amount> <Currency>` | Has outbound tax |
| [TheelUtil\#6258](https://dueutil.org) | `!exchange <Amount> <Currency> <TUT/TTC/TUP>` | Send/Receive limited to 10 transactions per 24h, sending limit exists |

## Can I get/spend Discoins?

No. Discoin only exists during the transaction process and statistics: As a universal _unit_ for calculating currency, it is only used for calculating exchange rates as well as currency reserves. The real world equivalent example would be [XDR](https://en.wikipedia.org/wiki/Special_drawing_rights).

## Can I have a transaction record?

[https://dash.discoin.zws.im/](https://dash.discoin.zws.im/)

## I did not receive my payment!

1. Check [the Transaction Record](https://dash.discoin.zws.im/). If it says the transaction isn't handled, the receiving bot hasn't processed it yet.
2. If it has been more than 5 minutes and the transaction still isn't handled, check if there are any restrictions in place, which are usually announced on this page as well as the support server. Still no avail? Contact the developer\(s\) of the receiving bot.

## Suggested uses of each currency

Here's a table on the earning and spending mechanisms of each bot.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>Bot (Currency</p>
        <p>Code)</p>
      </th>
      <th style="text-align:left">How to Earn (Except voting and daily)</th>
      <th style="text-align:left">How to Spend</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">BattleBanana (BBT)</td>
      <td style="text-align:left">Quests and <code>!blackjack</code>
      </td>
      <td style="text-align:left"><code>!shop</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ChaosRPG (CPG)</td>
      <td style="text-align:left"><code>?battle</code>
      </td>
      <td style="text-align:left"><code>?shop</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Dice (OAT)</td>
      <td style="text-align:left"><code>$$dice-game</code> if won</td>
      <td style="text-align:left">Gambling in <code>$$dice-game</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Digimon Universe (BIT)</td>
      <td style="text-align:left"><code>d-battle</code>
      </td>
      <td style="text-align:left"><code>d-shop</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">~ (CRD)</td>
      <td style="text-align:left">For now unobtainable, besides from Discoin.
      </td>
      <td style="text-align:left"><code>d-shop</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">DiscordTel (DTS)</td>
      <td style="text-align:left"><code>&gt;lottery</code> if won</td>
      <td style="text-align:left"><a href="https://discordtel.austinhuang.me/en/latest/Payment/">Renewing your DiscordTel service</a>, <code>&gt;message</code> as
        well as <code>&gt;lottery</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Elite Looter (ELT)</td>
      <td style="text-align:left"><code>;open</code>ing crates gained by chatting, also <code>;games</code>
      </td>
      <td style="text-align:left"><code>;shop</code>ing upgrades as well as playing <code>;games</code> to
        get more crates</td>
    </tr>
    <tr>
      <td style="text-align:left">KekBot (KEK)</td>
      <td style="text-align:left"><code>$lottery</code> if won, also <code>$game</code>
      </td>
      <td style="text-align:left"><code>$shop</code>ing profile card decorations as well as<code>$lottery</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Gami (GBC)</td>
      <td style="text-align:left"><code>-beg</code>, <code>-steal</code>, <code>-work</code>
      </td>
      <td style="text-align:left"><code>-gamble</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Lootcord (LCN)</td>
      <td style="text-align:left"><code>t-trivia</code>, <code>t-scramble</code>, <code>t-gamble</code>as
        well as by<code>t-sell</code> items/boxes and<code>t-use</code> items to
        loot other users, as well as <a href="https://github.com/blobfysh/Lootcord/wiki/Clans">depositing in a clan to earn interest</a>,
        see <a href="https://lootcord.com/faq">FAQ</a>
      </td>
      <td style="text-align:left"><code>t-shop</code>, <code>t-bm</code>, <code>t-trade</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Murder Mystery Bot (MMB)</td>
      <td style="text-align:left">Typing <code>mm!globalgames</code> daily</td>
      <td style="text-align:left"><code>mm!globalgames</code> =&gt; Shop</td>
    </tr>
    <tr>
      <td style="text-align:left">Nova (SPN)</td>
      <td style="text-align:left"><code>n!work</code>, as well as taking chances in <code>n!crime</code> and <code>n!rob</code>
      </td>
      <td style="text-align:left"><code>n!shop</code> for backgrounds</td>
    </tr>
    <tr>
      <td style="text-align:left">Pinocchio (PIC)</td>
      <td style="text-align:left">Chat rewards, as well as coin drops if enabled</td>
      <td style="text-align:left"><code>=waifu</code> (Buy discounted ones through <code>=rr</code>) as well
        as <code>=paidroles</code> if set</td>
    </tr>
    <tr>
      <td style="text-align:left">Pollux (RBN)</td>
      <td style="text-align:left"><code>+betflip</code>, <code>+blackjack</code>, <code>+slots</code>
      </td>
      <td style="text-align:left"><code>+shop</code>ing crafting materials and profile decorations</td>
    </tr>
    <tr>
      <td style="text-align:left">TheelUtil (TUT)</td>
      <td style="text-align:left">Quests, <code>!joinjob</code>
      </td>
      <td style="text-align:left"><code>!shop</code> for upgrades</td>
    </tr>
    <tr>
      <td style="text-align:left">~ (TTC)</td>
      <td style="text-align:left">Quests</td>
      <td style="text-align:left"><code>!teamshop</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">~ (TUP)</td>
      <td style="text-align:left"><code>!prestige</code>
      </td>
      <td style="text-align:left"><code>!prestigeshop</code>
      </td>
    </tr>
  </tbody>
</table>## Credits \(aka. "How can I support Discoin?"\)

Discoin is a cooperative project, combining efforts of many developers from diverse backgrounds across the globe.

* Discoin v3 is written and hosted by [Jonah Snider](https://jonah.pw) \(Dice\). Subdomain provided by [Zero Width Shortener](https://zws.im). Consider supporting him on [Patreon](https://www.patreon.com/pizzafox) or [Open Collective](https://opencollective.com/zws) to help paying for server cost!
* The concept, math, and non-technical documentation of Discoin is developed by [Austin Huang](https://austinhuang.me) \(DiscordTel\), with help from [Mitchell Rademaker](https://github.com/mitchell3514) \(DiscordTel\).
* Currency graphics \(except Discoin logo\) created by [Lucas Flicky](http://lucasflicky.com/) \(Pollux\). Discoin logo created by ImRock \([Welcomer](https://welcomer.gg)\).
* [Ari Gami](https://github.com/dr-ari-gami) \(Gami\), [DeveloperAnonymous](https://github.com/DeveloperAnonymous) \(BattleBanana\), [Godson](https://github.com/Godson777) \(Kekbot\) and [Theelgirl](https://github.com/Theelgirl) \(TheelUtil\) contributed to the [libraries](developers/guide.md#libraries).
* [Discoin is open source.](https://github.com/discoin/api-v3) If you cannot contribute financially, consider contributing your time reviewing the code!
* And of course, you can easily support Discoin by spreading the word to the world! Convince the developers of your favourite bot\(s\) to implement Discoin by showing this guide to them.

