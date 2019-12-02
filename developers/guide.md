---
description: >-
  Want to provide more choices for spending your currency to your users? You've
  come to the right place!
---

# Guide

Want to provide more choices for spending your currency to your users? You've come to the right place!

## Step-by-Step

{% hint style="tip" %} We generally aim for **bots that have between 500 and 10000 servers.** Bots with more than 10000 servers are welcomed for now but may be restricted in terms of the amount of bots we accept in the future. Bots with less than 500 servers can only be accepted at an exceptional basis, but it does need a bare minimum of 100 servers. {% endhint %}

1. Apply for an API key [here](https://austinhuang.typeform.com/to/yABBz5).
2. Once approved, we'll discuss with you and determine an exchange rate, as well as limits.
3. Implement Discoin into your bot. 

The initial exchange rate is calculated through a general daily gain of an average user. Over time, the rate and limit can be adjusted, and it is recommended for bot owners to recommend statistics over their bot economies.

## Technology

A central API is used so that each participating bot can send requests and receive requests to process transactions.

Let's say a user wants to exchange A bot currency to B bot currency.

1. The user requests exchanging on A bot
2. In the API, A bot sends a message indicates that a transaction has been started.
3. API converts the currency and leaves a message waiting for B bot to pick up.
4. B bot picks the message up and finishes the transaction.
5. The user is notified by B bot indicates that the transaction has been finished.

