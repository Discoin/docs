---
description: >-
  Want to provide more choices for spending your currency to your users? You've
  come to the right place!
---

# Guide

Want to provide more choices for spending your currency to your users? You've come to the right place!

## Step-by-Step

1. Apply for an API key [here](https://austinhuang.typeform.com/to/yABBz5).
2. Once your approved, we'll discuss with you and determine an exchange rate, as well as limits.
3. Implement Discoin into your bot. 

## Technology

A central API is used so that each participating bot can send requests and receive requests to process transactions.

Let's say a user wants to exchange A bot currency to B bot currency.

1. The user requests exchanging on A bot
2. In the API, A bot sends a message indicates that a transaction has been started.
3. API converts the currency and leaves a message waiting for B bot to pick up.
4. B bot picks the message up and finishes the transaction.
5. The user is notified by B bot indicates that the transaction has been finished.

