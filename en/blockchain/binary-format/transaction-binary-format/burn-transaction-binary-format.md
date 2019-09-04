# Burn transaction binary format

## Binary format version 2

| Field order number | Field name | JSON field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Version flag | | Byte | 1 | Indicates that this is a transaction with a [data structure](/blockchain/transaction-data-structure.md) of version 2 or above. <br>The value has to be equal to 0 |
| 2 | Transaction type | type | Byte | 1 | ID of the [transaction type](/blockchain/transaction-type.md). <br>The value has to be equal to 6 |
| 3 | Version number | version | Byte | 1 | Version number of the data structure of the transaction.  <br>The value has to be equal to 2 |
| 4 | Network ID | chainId|Byte | 1 | Determines the network where the transaction will be published to. <br>84 for [test network](/blockchain/blockchain-network/test-network.md), 87 for [mainnet](/blockchain/blockchain-network/main-network.md) |
| 5 | Public key of sender | senderPublicKey | Array of bytes | 32 | Account public key of the sender |
| 6 | Token ID | assetId| Array of bytes | 32 | ID of the token to burn |
| 7 | Amount | amount | Long | 8 | Amount of tokens to burn |
| 8 | Fee | fee | Long | 8 | [Transaction fee](/blockchain/transaction-fee.md) in [ACRYLETTEs](/blockchain/token/acrylette.md) |
| 9 | Timestamp | timestamp | Long | 8 | Unix time of sending a transaction to the blockchain |
| 10 | Proofs | proofs | Array of [proofs](/blockchain/transaction-proof.md) | `S` | If the array is empty, then `S`= 3. <br>If the array is not empty, then `S` = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), where `N` is the number of proofs in the array, `P`<sub>n</sub> is the size on `N`-th proof in bytes. <br>The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |

## JSON representation of a transaction with binary format version 2

```json
{
  "type": 6,
  "version": 2,
  "chainId": 87,
  "senderPublicKey": "9GaQj7gktEiiS1TTTjGbVjU9bva3AbCiawZ11qFZenBX",
  "assetId": "FVxhjrxZYTFCa9Bd4JYhRqXTjwKuhYbSAbD2DWhsGidQ",
  "amount": 9999,
  "fee": 100000,
  "timestamp": 1548660675277,
  "proofs": [
    "61jCivdv3KTuTY6QHgxt4jaGrXcszWg3vb9TmUR26xv7mjWWwjyqs7X5VDUs9c2ksndaPogmdunHDdjWCuG1GGhh"
  ],  
  "id": "csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL",
  "sender": "3P9QZNrHbyxXj8P9VrJZmVu2euodNtA11UW",
  "height": 1370971
}
```

## Binary format version 1

| Field order number | Field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte | 1 | ID of the transaction type.The value has to be equal to 6 |
| 2 | Sender's public key | Array of bytes | 32 | Public key of the sender's account |
| 3 | Token ID | Array of bytes | 32 | ID of the token to burn |
| 4 | Amount | Long | 8 | Amount of tokens to burn |
| 5 | Fee | Long | 8 | Transaction fee in ACRYLETTE |
| 6 | Timestamp | Long | 8 | Unix time of sending a transaction to the blockchain |
| 7 | Signature | Array of bytes | 64 | [Transaction signature](/blockchain/transaction-signature.md) |
