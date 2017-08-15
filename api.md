# API
API documentation for Rewritten v1.

## GET /transaction
Retrieves unprocessed transactions. All retrieved transactions will be marked as "Processed".

### Header
`Authorization`: Your token.

### Successful Return
**200** An array of transactions. Example:

```json
[{
    "user": 155784937511976960,
    "timestamp": 1502829034,
    "source": "DTS",
    "amount": 1.2,
    "receipt": "jFcwnTy7oH5g7u0r9bXK"
},
{
    "user": 155784937511976960,
    "timestamp": 1502829034,
    "source": "DUT",
    "amount": 1,
    "receipt": "w6154hLZtdEj42f9v9Ap",
    "type": "refund"
}]
```
* `amount`: How much the user should be given on the destination (your) bot.
* `user`: Integer, the user who requested transaction.
* `receipt`: String, Receipt.
* `type`: Type of the transaction normally can be omitted but is needed for to mark refunds (future).

If no transactions, an empty array (`[]`) will be returned.

### Error Return
**401**

```json
{"status": "error", "reason": "unauthorized"}
```

## POST /transaction
Request a transaction.

### Header
`Authorization`: Your token.

### Body
```json
{
    "user": 155784937511976960,
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
    "receipt": "w6154hLZtdEj42f9v9Ap",
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
{"status": "declined", "reason" : "per-User limit exceeded", "currency": "DUT", "limit": 2500, "limitNow": 0}
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

**401**
```json
{"status": "error", "reason": "unauthorized"}
```

## POST /transaction/reverse
### Future feature.
Reject a transaction sent to your bot and allow the the source bot to refund the user.
Will create a transaction to the source bot marked as a "refund".

### Header
`Authorization`: Your token.

### Body
```json
{
    "receipt": "w6154hLZtdEj42f9v9Ap",
}
```

### Successful Return
**200**
```json
{"status": "ok", "refundAmount": 100}
```

* `refundAmount`: This should be the amount the user attempted to exchange to your bot (at the source bot).
It will be in the currency of the source bot.

### Rejection Return

#### Transaction does not exist
**400**
```json
{"status": "failed", "reason": "transaction not found"}
```
