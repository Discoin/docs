# Developer's Guide
Want to provide more choices for spending your currency to your users? You've come to the right place!

## Step-by-Step
1. Apply for an API key [here](https://austinhuang.typeform.com/to/yABBz5).
2. If approved, we'll discuss with you and determine an exchange rate, as well as limits.
3. Implent Discoin into your bot. The API documentation is [here]. Wrapper libraries will also be available soon.
4. Done!

## Technology
A central API is used so that each participating bot can send requests and receive requests to process transactions.

Let's say a user wants to exchange A bot currency to B bot currency.

1. The user requests exchanging on A bot
2. In the API, A bot sends a message indicates that a transaction has been started.
3. API converts the currency and leaves a message waiting for B bot to pick up.
3. B bot picks the message up and finishes the transaction.
4. The user is notified by B bot indicates that the transaction has been finished.
