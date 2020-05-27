---
description: Migration guide from MacDue's v2 to PizzaFox's v3.
---

# Implementation

This page describes key API methods used to initiate transactions within the new API \(Since [the auto-generated documentation](https://discoin.zws.im/docs) has several errors\). You're welcomed to test everything out yourself.

{% api-method method="get" host="https://discoin.zws.im" path="/transactions/:id" %}
{% api-method-summary %}
Get Transactions
{% endapi-method-summary %}

{% api-method-description %}
Retrieves transactions. All retrieved transactions will **NOT** be automatically marked as "Processed". A PATCH request \(described later\) will do so.  
API docs are mostly correct for this and are more detailed.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
Transaction ID.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="filter" type="string" required=false %}
Filter results of your query. If you don't specify this, the API returns _all_ transactions. If you only want relevant unprocessed transactions, you can put`filter=to.id||eq||ABC&filter=handled||eq||false` here \(gotta be URL encoded, of course\).
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
An array of transactions, or an object of transaction if :id is specified.
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

{% api-method method="post" host="https://discoin.zws.im" path="/transactions" %}
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
"Bearer " + your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="amount" type="number" required=true %}
Transaction amount in original currency.
{% endapi-method-parameter %}

{% api-method-parameter name="toId" type="string" required=true %}
String, 3-letter currency code representing the destination currency. It's `"toId"` not the past form of `"told"`.
{% endapi-method-parameter %}

{% api-method-parameter name="user" type="string" required=true %}
ID of user who requested the transaction.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Shows transaction details. Notice that it provides the transaction ID as well.
{% endapi-method-response-example-description %}

```javascript
{
	"id": "b9cd2775-f354-4b6c-9a8b-5ad24b8cc11d",
	"amount": 1000,
	"user": "210024244766179329",
	"handled": false,
	"timestamp": "2019-12-25T18:27:27.773Z",
	"payout": 100.1,
	"from": {
		"id": "DTS",
		"name": "Discordtel Credits"
	},
	"to": {
		"id": "OAT",
		"name": "Dice Oats"
	}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://discoin.zws.im" path="/transactions/:id" %}
{% api-method-summary %}
Process transactions
{% endapi-method-summary %}

{% api-method-description %}
Update a transaction, usually this means marking a transaction as processed.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Transaction ID.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
"Bearer " + your token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="handled" type="boolean" required=false %}
Should be `true` to mark this transaction as processed.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Shows updated transaction details.
{% endapi-method-response-example-description %}

```
{
	"id": "b9cd2775-f354-4b6c-9a8b-5ad24b8cc11d",
	"amount": 1000,
	"user": "210024244766179329",
	"handled": true,
	"timestamp": "2019-12-25T18:27:27.773Z",
	"payout": 100.1,
	"from": {
		"id": "DTS",
		"name": "Discordtel Credits"
	},
	"to": {
		"id": "OAT",
		"name": "Dice Oats"
	}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

