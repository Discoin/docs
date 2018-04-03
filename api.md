# Libraries
Plain lazy? Use our pre-made libraries!

* [Java](https://github.com/Godson777/Discoin4J)
* [Node.js](https://www.npmjs.com/package/discoin)
* [Python](https://pypi.python.org/pypi/discoin)

# API

API documentation for Rewritten v1.

All endpoints start with `http://discoin.sidetrip.xyz`. **Do NOT use HTTPS** or your authorization token will not be carried over.

## General errors

**400**


```json
{"status": "error", "reason": "invalid json"}
```
Your json was incorrect.
___

```json
{"status": "error", "reason": "invalid types"}
```
The types in your post were not correct.
For example you posted the user id as a long/int not a string.
___


```json
{"status": "error", "reason": "bad post"}
```
You data/json was correct but was missing/has improperly named varibles.
___


```json
{"status": "error", "reason": "invalid post"}
```
The page you POST-ed to did not exist.
___

```json
{"status": "error", "reason": "invalid get"}
```
The page you GET-ted to did not exist.
___

**401**

```json
{"status": "error", "reason": "unauthorized"}
```
Your token is invalid.


## GET /transaction**s**

Retrieves unprocessed transactions. All retrieved transactions will be marked as "Processed".

### Header

`Authorization`: Your token.

### Successful Return

**200** An array of transactions. Example:

```json
[{
    "user": "155784937511976960",
    "timestamp": 1502829034,
    "source": "DTS",
    "amount": 1.2,
    "receipt": "e7eed14463d00e05eca7075bbc89aa7be640e494"
},
{
    "user": "155784937511976960",
    "timestamp": 1502829034,
    "source": "DUT",
    "amount": 1,
    "receipt": "f951dae48f7ef5670270717fe57af9eb41b889f0",
    "type": "refund"
}]
```

* `amount`: How much the user should be given on the destination \(your\) bot.
* `user`: Integer, the user who requested transaction.
* `receipt`: String, Receipt.
* `type`: Type of the transaction normally can be omitted but is needed for to mark refunds \(future\).

If no transactions, an empty array \(`[]`\) will be returned.

## GET /transaction/:receipt

Retrieves transaction info based off receipt.

### Params

`:receipt`: Your receipt ID.

### Header

`Authorization`: Your token.

### Successful Return

**200**

```json
{
   "user":"132315148487622656",
   "timestamp":1503428678,
   "source":"DUT",
   "target":"DTS",
   "receipt":"3013edf87bf5a369621fd6065b1454ea7ba71464",
   "amountSource":10,
   "amountDiscoin":120,
   "amountTarget":10,
   "processed":true,
   "processTime":1503429255,
   "reversed":true,
   "type":"normal"
}
```

//todo

**404**

```json
{"status":"error","reason":"transaction not found"}
```

## POST /transaction

Request a transaction.

### Header

`Authorization`: Your token.

### Body

```json
{
    "user": "155784937511976960",
    "amount": 1,
    "exchangeTo": "DUT"
}
```

* `user`: Integer, the ID of the user who requested the transaction
* `amount`: Integer, transaction amount in originated currency
* `exchangeTo`: String, 3-letter currency code representing the destination currency. Can be lowercased.

### Successful Return

**200**

```json
{
    "status": "approved",
    "receipt": "dca311df716ad4a6b734e3b92f0b58d797abd98c",
    "limitNow": 4999,
    "resultAmount": 1
}
```

* `receipt`: String, Receipt ID
* `limitNow`: Integer, Remaining balance of Daily Per-User Limit for this user
* `resultAmount`: Integer, How much the amount exchanged will be worth in destination currency.

### Rejection Return

**403**

#### User is not verified

```json
{"status": "declined", "reason": "verify required"}
```

#### User exceeded Daily Per-User Limit

```json
{"status": "declined", "reason" : "per-user limit exceeded", "currency": "DUT", "limit": 2500}
```

#### User exceeded Daily Total Limit

```json
{"status": "declined", "reason" : "total limit exceeded", "currency": "DUT", "limit": 100000}
```

### Error Return

**400**

```json
{"status": "error", "reason": "invalid amount"}
```

```json
{"status": "error", "reason": "invalid destination currency"}
```

```json
{"status": "error", "reason": "amount NaN"}
```

## GET /rates.json
No authorization needed.

### Return

```json
[
   {
      "DueUtil":{
         "currencyCode":"DUT",
         "toDiscoin":1.5,
         "fromDiscoin":0.3
      }
   },
   {
      "DiscordTel":{
         "currencyCode":"DTS",
         "toDiscoin":1,
         "fromDiscoin":1
      }
   },
   {
      "PyButt":{
         "currencyCode":"PYB",
         "toDiscoin":1,
         "fromDiscoin":1
      }
   }
]
```

## POST /transaction/reverse

Reject a transaction sent to your bot and allow the the source bot to refund the user.  
Will create a transaction to the source bot marked as a "refund".

### Header

`Authorization`: Your token.

### Body

```json
{
    "receipt": "e7eed14463d00e05eca7075bbc89aa7be640e494"
}
```

### Successful Return

**200**

```json
{"status": "ok", "refundAmount": 100}
```

* `refundAmount`: This should be the amount the user attempted to exchange to your bot \(at the source bot\).
  It will be in the currency of the source bot.

### Fails Return


**400**
```json
{"status": "failed", "reason": "cannot refund a refund"}
```

```json
{"status": "failed", "reason": "transaction already reversed"}
```

```json
{"status": "failed", "reason": "invalid receipt"}
```
**403**

```json
{"status": "failed", "reason": "transaction must be to your bot"}
```
**404**

```json
{"status": "failed", "reason": "transaction not found"}
```





