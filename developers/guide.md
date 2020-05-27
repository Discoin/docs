---
description: >-
  Want to provide more choices for spending your currency to your users? You've
  come to the right place!
---

# Guide

## Why should my bot adopt Discoin?

Let's keep it short and sweet.

1. **Rewarding** - By giving more ways to spend, you motivate users to keep earning your currencies as they will have multiple goals to reach, thus keeping them busy. As well, the investment aspect of [dynamic rates ](../untitled.md)could bring further amusement!
2. **Balancing** - Having multiple options to spend the currency on means users must balance over these options. They'll also be less likely to keep the currencies to themselves, thus allowing the leaderboard to refresh over time!
3. **Beneficial** - By going hand on hand with large bots, your bot will grow its server count just as they do! And you don't need to do the hard lifting of developing similar features just to be "on par" with other bots. Make your bot unique, and leave the economy to us!

And a BONUS: **Educating** - By giving a taste of investment with gains and losses, Discoin will teach users basic concepts of saving that will benefit them in real life!

## Step-by-Step

{% hint style="success" %}
We accept **verified** bots with more than **250** servers.
{% endhint %}

1. Apply for an API key [here](https://austinhuang.typeform.com/to/yABBz5).
2. Once approved, we'll discuss with you and determine an exchange rate.
3. Implement Discoin into your bot. 

The initial exchange rate is calculated through the daily gain of an average user. Over time, the rate and limit can be adjusted, and it is recommended for bot owners to collect statistics over their bot economies.

## Technology

A central API is used so that each participating bot can send and receive requests to process transactions.

Let's say a user wants to exchange A bot currency to B bot currency.

1. The user requests exchanging on A bot
2. In the API, A bot [sends a request](implementation.md#create-new-transaction) indicates that a transaction has been started.
3. API converts the currency and creates a transaction waiting for B bot to pick up.
4. B bot [picks the transaction up](implementation.md#get-transactions), [marks it](implementation.md#process-transactions), and finishes the transaction.
5. The user is notified by B bot indicates that the transaction has been finished.

So you need 2 parts: A command to initiate a transaction, and a module \(cron job\) to process incoming transactions. Of course, should you want to create a command to show real time exchange rates, [that's no problem.](https://discoin.zws.im/docs/#/currencies/getManyBase) We also have libraries to assist you...

## Libraries

* [Java](https://github.com/godson777/discoin4j)
* [JavaScript](https://npmjs.com/@discoin/scambio)
* [Python](https://pypi.org/project/discoin/)

## API Reference

Key endpoints are listed here. If you want to look at the entire API specs, go to [https://discoin.zws.im/docs](https://discoin.zws.im/docs).

