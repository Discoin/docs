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
    "fromTime": "Sun Aug 13 2017 12:13:04 GMT-0700 (PDT)",
    "from": "DUT",
    "to": "DTS",
    "amount": 1.2,
    "id": "jFcwnTy7oH5g7u0r9bXK"
},
{
    "user": 155784937511976960,
    "fromTime": "Sun Aug 13 2017 11:39:01 GMT-0700 (PDT)",
    "from": "DTS",
    "to": "DTS",
    "amount": 1,
    "id": "w6154hLZtdEj42f9v9Ap"
}]
```
* `resultAmount`: Integer, How much the amount exchanged will be worth in destination currency.
* `user`: Integer, the user who requested transaction.
* `id`: String, Receipt ID.

If no transactions, an empty array (`[]`) will be returned.

### Error Return
**401**

```json
{"status": "error", "reason": "Unauthorized"}
```

## POST /transaction
Request a transaction.

### Header
`Authorization`: Your token.

### Body
```json
{
    "user_id": 155784937511976960,
    "amount" 1,
    "exchangeTo": "DUT"
}
```

* `user_id`: Integer, the ID of the user who requested the transaction
* `amount`: Integer, transaction amount in originated currency
* `exchangeTo`: String, 3-letter currency code representing the destination currency. Can be lowercased.

### Successful Return

**200**

```json
{
    "status": "approved",
    "receipt": "w6154hLZtdEj42f9v9Ap",
    "limitNow": 4999,
    "resultAmount" 1
}
```

* `receipt`: String, Receipt ID
* `limitNow`: Integer, Remaining balance of Daily Per-User Limit for this user
* `resultAmount`: Integer, How much the amount exchanged will be worth in destination currency.

### Rejection Return

**403**

#### User is not verified
```json
{"status": "declined", "reason": "User is not verified. Go to https://discoin.disnodeteam.com/verify"}
```

#### User exceeded Daily Per-User Limit
```json
{"status": "declined", "reason" : "Daily Per-User Limit exceeded.", "currency": "DUT", "limit": 2500, "limitNow": 0}
```

#### User exceeded Daily Total Limit
```json
{"status": "declined", "reason" : "Daily Total Limit exceeded.", "currency": "DUT", "limit": 100000}
```

### Error Return

**400**
```json
{"status": "error", "reason": "Invalid amount"}
```
```json
{"status": "error", "reason": "Invalid destination currency"}
```

**401**
```json
{"status": "error", "reason": "Unauthorized"}
```
