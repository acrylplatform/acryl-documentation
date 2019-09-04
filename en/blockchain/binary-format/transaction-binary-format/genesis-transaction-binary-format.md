# Genesis transaction binary format

## Binary format version 1

| Field order number | Field name | JSON field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Transaction type |type| Byte | 1 | ID of the [transaction type](/blockchain/transaction-type.md).<br>The value must be 1 |
| 2 | Timestamp | timestamp | Long | 8 | Unix time of sending a transaction to the blockchain |
| 3 | Account address | recipient | Array of bytes | 26 |  |
| 4 | Amount | amount | Long | 8 | The number of [ACRYL](/blockchain/token/acryl.md) that will be credited to the [account](/blockchain/account.md) |
| 5 | Fee |fee | Long | 8 | [Transaction fee](/blockchain/transaction-fee.md) in [ACRYLETTEs](/blockchain/token/acrylette.md) |
| 6 | Signature | signature | Array of bytes | 64 | [Transaction signature](/blockchain/transaction-signature.md) |

## JSON representation of a transaction with binary format version 1 <a id="json"></a>

```json
{ 
   "type":1,
   "timestamp":2686163577562422135,
   "recipient":"3MowSBodyYH25xayqCWoCtY7KBHc7wvv8cs",
   "amount":3074457345618258602,
   "id":"3E2qJVdMC1wzFEZwCyejA1a1AwDv52wwi2CRPaf5uNw3WTQYNW9C32cxGWBehJi2ED5f2YtYg2RJRcAX2U3wPhxy",
   "fee":0,
   "signature":"3E2qJVdMC1wzFEZwCyejA1a1AwDv52wwi2CRPaf5uNw3WTQYNW9C32cxGWBehJi2ED5f2YtYg2RJRcAX2U3wPhxy",
}
```
