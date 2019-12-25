---
description: Migration guide from MacDue's v2 to PizzaFox's v3.
---

# Rewrite Migration Guide

This page describes key API methods used within the new API \(Since [the auto-generated documentation](https://discoin.zws.im/docs) did not do a good job describe it\). You're welcomed to test everything out yourself.

{% api-method method="get" host="https://discoin.zws.im" path="/transactions" %}
{% api-method-summary %}
Get Transactions
{% endapi-method-summary %}

{% api-method-description %}
Retrieves unprocessed transactions. All retrieved transactions will **NOT** be automatically marked as "Processed". A PATCH request \(described later\) will do so.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
"Bearer " + Your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="s" type="string" required=false %}
Search queries. By default, the API returns _all_ transactions. If you only want relevant unprocessed transactions, you can put`{"to.id": "<currency code>", "handled": false}` here \(Gotta be HTML-encoded, of course\). \(Other parameters also exist, check API docs.\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
An array of transactions.
{% endapi-method-response-example-description %}

```javascript
[
  {
    "id": "188986c9-7f50-479b-a447-74ccbb9ab383",
    "amount": 10,
    "user": "210024244766179329",
    "handled": true,
    "timestamp": "2019-12-25T07:21:54.941Z",
    "payout": 1,
    "from": {
      "id": "OAT",
      "name": "Dice Oats"
    },
    "to": {
      "id": "DTS",
      "name": "Discordtel Credits"
    }
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://discoin.sidetrip.xyz" path="/transaction/:receipt" %}
{% api-method-summary %}
Get Transaction
{% endapi-method-summary %}

{% api-method-description %}
Retrieves transaction info based off receipt.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="receipt" type="string" required=true %}
The receipt you want to look up.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Transaction information.
{% endapi-method-response-example-description %}

```javascript
{
    "amountDiscoin": 120,
    "amountSource": 10,
    "amountTarget": 10,
    "processTime": 1503429255,
    "processed": true,
    "receipt": "3013edf87bf5a369621fd6065b1454ea7ba71464",
    "reversed": true,
    "source": "DUT",
    "target": "DTS",
    "timestamp": 1503428678,
    "type": "normal",
    "user": "132315148487622656"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No transaction was found.
{% endapi-method-response-example-description %}

```javascript
{
    "reason": "transaction not found",
    "status": "error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://discoin.sidetrip.xyz" path="/transaction" %}
{% api-method-summary %}
Create New Transaction
{% endapi-method-summary %}

{% api-method-description %}
Request a transaction.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="amount" type="integer" required=true %}
Transaction amount in original currency.
{% endapi-method-parameter %}

{% api-method-parameter name="exchangeTo" type="integer" required=true %}
String, 3-letter currency code representing the destination currency. Case insensitive.
{% endapi-method-parameter %}

{% api-method-parameter name="user" type="string" required=true %}
ID of user who requested the transaction
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "limitNow": 4999,
    "receipt": "dca311df716ad4a6b734e3b92f0b58d797abd98c",
    "resultAmount": 1,
    "status": "approved"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid data \(amount or destination currency\)
{% endapi-method-response-example-description %}

```javascript
{
    "reason": "invalid amount",
    "status": "error"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
User rejections.
{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="not verified" %}
```javascript
{
    "reason": "verify required",
    "status": "declined"
}
```
{% endtab %}

{% tab title="exceeded daily per user limit" %}
```javascript
{
    "currency": "DUT",
    "limit": 2500,
    "reason": "per-user limit exceeded",
    "status": "declined"
}
```
{% endtab %}

{% tab title="exceeded daily total limit" %}
```javascript
{
    "currency": "DUT",
    "limit": 100000,
    "reason": "total limit exceeded",
    "status": "declined"
```
{% endtab %}
{% endtabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://discoin.sidetrip.xyz" path="/rates.json" %}

{% api-method method="post" host="http://discoin.sidetrip.xyz" path="/transaction/reverse" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
Reject a transaction sent to your bot and allow the the source bot to refund the user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="receipt" type="string" required=true %}
The receipt of the transaction you want to reverse.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Creates a transaction to the source bot marked as a "refund".
{% endapi-method-response-example-description %}

```javascript
{
    "refundAmount": 100,
    "status": "ok"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
You attempted to reverse a transaction that is a refund, already is reversed, or doesn't exist.
{% endapi-method-response-example-description %}

```javascript
{
    "reason": "invalid receipt",
    "status": "failed"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
You attempted to reverse a transaction from another bot.
{% endapi-method-response-example-description %}

```javascript
{
    "reason": "transaction must be to your bot",
    "status": "failed"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
You attempted to reverse a transaction that couldn't be found.
{% endapi-method-response-example-description %}

```javascript
{
    "reason": "transaction not found",
    "status": "failed"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

