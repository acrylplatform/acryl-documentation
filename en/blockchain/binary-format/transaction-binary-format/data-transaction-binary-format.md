# Data transaction binary format

## Binary format version 1

| Field order number | Field name | JSON field name  | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Version flag | | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Indicates that the current transaction has [data structure](/blockchain/binary-format/transaction-binary-format.md) of version 2 or above. The value must be 0 |
| 2 | Transaction type | type | [Byte](/blockchain/blockchain/blockchain-data-types.md)  | 1 | ID of the [transaction type](/blockchain/transaction-type.md). The value must be 12 |
| 3 | Version | version | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Version number of the data structure of the transaction. The value must be 1 |
| 4 | Public key of sender | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | Account public key of the sender |
| 5 | Length of the data array | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | |
| 6.1 | Key 1 length | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | |
| 6.2 | Key 1 | key | [String](/blockchain/blockchain/blockchain-data-types.md) | Up to 4 × `L` | `L` is a key length |
| 6.3 | Value 1 type | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | 0 — integer <br> 1 — boolean <br>2 — array of bytes <br> 3 — string |
| 6.4 |  Value 1 length |   |  [Short](/blockchain/blockchain/blockchain-data-types.md) | 2  | This field is present only if the value is of type of array of bytes or a string. <br>If the value is of type of integer or a boolean, this field should not be included in the data structure  |
| 6.5 | Value 1 | value | One of the following: <ul><li> [Int](/blockchain/blockchain/blockchain-data-types.md)</li><li> [Boolean](/blockchain/blockchain/blockchain-data-types.md)</li> <li>Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)]</li> <li>[String](/blockchain/blockchain/blockchain-data-types.md) </li></ul> | Depends on the size of the value | |
| 6.6 | Key 2 length | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | |
| 6.7 | Key 2 | key | [String](/blockchain/blockchain/blockchain-data-types.md) | Up to 4 × `L` | `L` is a key length |
| 6.8 | Value 2 type | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | 0 — integer <br>1 — boolean <br> 2 — array of bytes <br> 3 — string |
| 6.9 |  Value 2 length |   |  [Short](/blockchain/blockchain/blockchain-data-types.md) |  2 | This field is present only if the value is of type of array of bytes or a string. <br>If the value is of type of integer or a boolean, this field should not be included in the data structure |
| 6.10| Value 2 | value | One of the following: <ul><li> [Int](/blockchain/blockchain/blockchain-data-types.md)</li><li> [Boolean](/blockchain/blockchain/blockchain-data-types.md)</li> <li>Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)]</li> <li>[String](/blockchain/blockchain/blockchain-data-types.md) </li></ul>  | Depends on the size of the value | |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| ... | ... | ... | ... | ... | ... |
| 6.[5 × N - 4] | N-th key length | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | |
| 6.[5 × N - 3] | N-th key | key | [String](/blockchain/blockchain/blockchain-data-types.md) | Up to 4 × `L` | `L` is a key length |
| 6.[5 × N - 2] | N-th value type | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | 0 — integer <br>1 — boolean <br> 2 — array of bytes <br>3 — string |
| 6.[5 × N - 1] | N-th value length   |   | [Short](/blockchain/blockchain/blockchain-data-types.md)  | 2  |  This field is present only if the value is of type of array of bytes or a string. <br>If the value is of type of integer or a boolean, this field should not be included in the data structure |
| 6.[5 × N] | N-th value | value | One of the following: <ul><li> [Int](/blockchain/blockchain/blockchain-data-types.md)</li><li> [Boolean](/blockchain/blockchain/blockchain-data-types.md)</li> <li>Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)]</li> <li>[String](/blockchain/blockchain/blockchain-data-types.md) </li></ul>  | Depends on the size of the value | |
| 7 | Timestamp | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | Unix time of sending a transaction to the blockchain |
| 8 | Fee | fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | [Transaction fee](/blockchain/transaction/transaction-fee.md) in [WAVELETs](/blockchain/token/wavelet.md) |
| 9 | Proofs | proofs | Array of [proofs](/blockchain/transaction/transaction-proof.md) | `S` | If the array is empty, then `S` = 3. If the array is not empty, then `S` = 3 + 2 × `N` + (`P1` + `P2` + ... + `P`<sub>`n`</sub>), where `N` is the number of proofs in the array, `P`<sub>`n`</sub> is the size of `N`-th proof in bytes. The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |

## JSON representation of a transaction with binary format version 1 <a id="#json-representation"></a>

```json
{
   "type":12,
   "version":1,
   "senderPublicKey":"5AzfA9UfpWVYiwFwvdr77k6LWupSTGLb14b24oVdEpMM",
   "data":[
      {
         "key":"int",
         "type":"integer",
         "value":24
      },
      {
         "key":"isWeekend",
         "value":true,
         "type":"boolean"
      },
      {
         "key":"blob",
         "value":"base64:BzWHaQU",
         "type":"binary"
      },
      {
         "key":"My poem",
         "value":"Oh Waves!",
         "type":"string"
      }
   ],
   "timestamp":1520945679531,
   "fee":100000,
   "proofs":[
      "4huvVwtbALH9W2RQSF5h1XG6PFYLA6nvcAEgv79nVLW7myCysWST6t4wsCqhLCSGoc5zeLxG6MEHpcnB6DPy3XWr"
   ],
   "id":"CwHecsEjYemKR7wqRkgkZxGrb5UEfD8yvZpFF5wXm2Su",
   "sender":"3FjTpAg1VbmxSH39YWnfFukAUhxMqmKqTEZ",
   "height":303
}
```
