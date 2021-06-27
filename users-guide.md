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
2. Your transaction will be converted [at the rates effective at the moment](https://dash.discoin.zws.im/#/currencies). After a transaction, the rates will [adjust itself](untitled.md).
3. Within 5 minutes, the destination bot will receive your transaction. [Unless...?](users-guide.md#i-did-not-receive-my-payment)

### Commands List

* `<Currency>` means 3-letter currency codes listed [here](https://dash.discoin.zws.im/#/currencies). Exchange rates are listed there too.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Bot Name</th>
      <th style="text-align:left">Command</th>
      <th style="text-align:left">Note</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="https://dueutil.xyz">BattleBanana#0764</a>
      </td>
      <td style="text-align:left"><code>!exchange &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Max 500k BBT per transaction</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://top.gg/bot/603974948335124491">ChaosRPG#3409</a>
      </td>
      <td style="text-align:left"><code>?convert &lt;Amount&gt; &lt;CURRENCY&gt;</code>
      </td>
      <td style="text-align:left">Rates: <code>?rates</code>.
        <br />Must create account:<code>?start</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://dice.js.org">Dice#6134</a>
      </td>
      <td style="text-align:left"><code>$$convert-oats &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Rates: <code>$$discoin-rates</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://dtel.austinhuang.me">DTel#6675</a>
      </td>
      <td style="text-align:left"><code>&gt;convert &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Command without argument for rates</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="http://sjustein.com/html/elitelooter.html">Elite Looter#8634</a>
      </td>
      <td style="text-align:left"><code>;exchange &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Info: <code>;discoin</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://discordbots.org/bot/213151748855037953">KekBot#2918</a>
      </td>
      <td style="text-align:left"><code>$shop</code> then react 3</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://lootcord.com">Lootcord#6294</a>
      </td>
      <td style="text-align:left"><code>t-convert &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Send/Receive limited to 1 million LCN per day</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://top.gg/bot/319204121393496064">Murder Mystery Bot#7898</a>
      </td>
      <td style="text-align:left"><code>mm!convert &lt;Currency&gt; &lt;Amount&gt;</code>
      </td>
      <td style="text-align:left">Must create account:<code>mm!globalgames</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://top.gg/bot/460952742672990217">Nova#2243</a>
      </td>
      <td style="text-align:left"><code>n!convert &lt;Currency&gt; &lt;Amount&gt;</code>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://pinocchiobot.xyz/">Pinocchio#5540</a>
      </td>
      <td style="text-align:left"><code>=exchange &lt;Amount&gt; &lt;Currency&gt;</code>
      </td>
      <td style="text-align:left">Info: <code>=discoin</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://top.gg/bot/648065060559781889">Restaurant#4079</a>
      </td>
      <td style="text-align:left"><code>r!dsc exchange &lt;Currency&gt; &lt;Amount&gt;</code>
      </td>
      <td style="text-align:left">Rates: <code>r!dsc bots</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://dueutil.org">TheelUtil#6258</a>
      </td>
      <td style="text-align:left"><code>!exchange &lt;Amount&gt; &lt;Currency&gt; &lt;TUT/TTC/TUP&gt;</code>
      </td>
      <td style="text-align:left">Send/Receive limited to 10 transactions per 24h, sending limit exists</td>
    </tr>
  </tbody>
</table>

## Can I get/spend Discoins?

No. Discoin only exists during the transaction process and statistics: As a universal _unit_ for calculating currency, it is only used for calculating exchange rates as well as currency reserves. The real world equivalent example would be [XDR](https://en.wikipedia.org/wiki/Special_drawing_rights).

## Can I have a transaction record?

[https://dash.discoin.zws.im/\#/transactions](https://dash.discoin.zws.im/#/transactions)

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
      <td style="text-align:left">DTel (DTS)</td>
      <td style="text-align:left"><code>&gt;lottery</code> if won</td>
      <td style="text-align:left"><a href="https://dtel.austinhuang.me/en/latest/Payment/">Renewing your DTel service</a>, <code>&gt;message</code> as
        well as <code>&gt;lottery</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Elite Looter (ELT)</td>
      <td style="text-align:left"><code>;open</code>ing crates gained by chatting, also <code>;games</code>
      </td>
      <td style="text-align:left"><code>;shop</code>ing upgrades as well as <code>;games</code> to get more
        crates</td>
    </tr>
    <tr>
      <td style="text-align:left">KekBot (KEK)</td>
      <td style="text-align:left"><code>$lottery</code> if won, also <code>$game</code>
      </td>
      <td style="text-align:left"><code>$shop</code> profile decorations as well as<code>$lottery</code>
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
      <td style="text-align:left"><code>n!shop</code> for profile decorations</td>
    </tr>
    <tr>
      <td style="text-align:left">Pinocchio (PIC)</td>
      <td style="text-align:left">Chat rewards, as well as coin drops if enabled</td>
      <td style="text-align:left"><code>=waifu</code>, <code>=rr</code>, as well as <code>=paidroles</code> if
        set</td>
    </tr>
    <tr>
      <td style="text-align:left">Restaurant (RBC)</td>
      <td style="text-align:left"><code>r!work</code>, <code>r!slots</code>, <code>r!trivia</code>, <code>r!beg</code>,
        as well as receiving 50% from other users&apos; <code>r!dine</code> orders
        in your restaurant</td>
      <td style="text-align:left"><code>r!buy</code> and <code>r!dine</code>
      </td>
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
</table>

## Credits \(aka. "How can I support Discoin?"\)

Discoin is a cooperative project, combining efforts of many developers from diverse backgrounds across the globe.

* Discoin v3 is written and hosted by [Jonah Snider](https://jonah.pw) \(Dice\). Subdomain provided by [Zero Width Shortener](https://zws.im). Consider supporting him on [Patreon](https://www.patreon.com/pizzafox) or [Open Collective](https://opencollective.com/zws) to help paying for server cost!
* The concept, math, and non-technical documentation of Discoin is developed by [Austin Huang](https://austinhuang.me) \(DTel\), with help from [Mitchell Rademaker](https://github.com/mitchell3514) \(DTel\).
* Currency graphics \(except Discoin logo\) created by [Lucas Flicky](http://lucasflicky.com/) \(Pollux\). Discoin logo created by ImRock \([Welcomer](https://welcomer.gg)\).
* [Ari Gami](https://github.com/dr-ari-gami), [DeveloperAnonymous](https://github.com/DeveloperAnonymous) \(BattleBanana\), [Godson](https://github.com/Godson777) \(Kekbot\) and [Theelgirl](https://github.com/Theelgirl) \(TheelUtil\) contributed to the [libraries](developers/guide.md#libraries).
* [Discoin is open source.](https://github.com/discoin/api-v3) If you cannot contribute financially, consider contributing your time reviewing the code!
* And of course, you can easily support Discoin by spreading the word to the world! Convince the developers of your favourite bot\(s\) to implement Discoin by showing this guide to them.

