# ReissueTransaction

Structure of a [reissue transaction](/blockchain/transaction-type/reissue-transaction.md).

## Constructor

``` ride
ReissueTransaction(quantity: Int, assetId: ByteVector, reissuable: Boolean, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | quantity | Int | Amount of [tokens](/blockchain/token.md) |
| 2 | assetId | ByteVector | ID of a token |
| 3 | reissuable | Boolean | Reissue ability flag |
| 4 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 5 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 6 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 7 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 8 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 9 | senderPublicKey | ByteVector | Account public key of a sender |
| 10 | bodyBytes | ByteVector | Transaction's array of bytes |
| 11 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
