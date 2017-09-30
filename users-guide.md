# Discoin Guide for Users

This guide contains frequently asked questions during Discoin transactions.

## How can I exchange currency?
Before you can exchange currency, you must [verify yourself](http://discoin.sidetrip.xyz/verify). After verification, refer to the table below.

### Commands List
* `<Currency>` means 3-letter currency codes listed [here](http://discoin.sidetrip.xyz/rates).
* Currency exchange rates are listed [here](http://discoin.sidetrip.xyz/rates), also [here](#current-rates)
* For bot invites/supports, click [here](/austinhuang0131/Discoin/wiki/List-of-Participants).

|Bot Name|Command|Note|
|-|-|-|
|DiscordTel#0757|`>convert <Amount> <Currency>`||
|DueUtil#3321|`!exchange <Amount> <Currency>`||
|Elite Looter#8634|`;exchange <Amount> <Currency>`|Info: `;discoin`|
|Pollus#9069|`+exchange <Amount> <Currency>`|`p.exchange` also|
|PyButt#6485|`py!exchange <Amount> <Currency>`||
|SmoreBot#0560|`s.convert <Amount> <Currency>`|`s.transfer` also|

## Why do I need to give out my email?
To prevent users bypassing daily limits by making multiple accounts, we use your email address to filter some of them out. **We do not record or store your email address**, as indicated in the source code. [We have a privacy policy, just in case.](https://github.com/austinhuang0131/Discoin/wiki/ToS-&-Privacy#privacy-policy)

## Can I spend Discoins?
No. Discoin only exists during the transaction process and statistics: As a temporary currency, Discoin can only be converted from one currency to another; as a universal *unit* for calculating currency, it is only used for calculating exchange rates.

## Can I have a transaction record?
[Yes.](http://discoin.sidetrip.xyz/record) You can view all transactions made through Discoin in the current calendar month. For transaction records before the current month, contact any core developers or participants in the [Discoin server](https://discord.gg/NExXSDH).

## Why are there transaction limits?
While some bots have interesting features, they are vulnerable once the "challenge" in it has disappeared: For example, if you are playing RPG on a bot, one of your goals would be earning money to improve yourself. Discoin is supposed to be a tool helping you to reach that goal, not *a hack reaching the goal directly for you*. Without transaction limit, you will lose the power to continuing playing RPG on the bot.

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

## Current Rates
|Bot Name|Currency Name|From 1 Discoin|To 1 Discoin|Note|
|-|-|-|-|-|
|DiscordTel#0757|~Credits (DTS)|1|1||
|DueUtil#3321|~Tokens (DUT)|0.2|≈0.67|Only accepts integer as result amount, or refund|
|Elite Looter#8634|~Coins (ELT)|≈0.59|≈0.59||
|Pollus#9069|Rubines (RBN)|1.25|1.25||
|PyButt#6485|PyBucks (PYB)|1|1||
|SmoreBot#0560|SmoreCash (SBT)|1|1||