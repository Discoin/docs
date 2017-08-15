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
If no transactions, an empty array (`[]`) will be returned.

### Error Return
**401**

```json
{"status": "error", "reason": "Unauthorized"}
```
