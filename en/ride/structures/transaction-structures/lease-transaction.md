# LeaseTransaction

Structure of a [lease transaction](/blockchain/transaction-type/lease-transaction.md).

## Constructor

``` ride
LeaseTransaction(amount: Int, recipient: Address|Alias, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | amount | Int | Amount of [tokens](/blockchain/token.md) to lease |
| 2 | recipient | Address&#124;Alias | [Address](/blockchain/address.md) or [alias](/blockchain/alias.md) of the leasing recipient |
| 3 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 4 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 5 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 6 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 7 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 8 | senderPublicKey | ByteVector | Account public key of a sender |
| 9 | bodyBytes | ByteVector | Transaction's array of bytes |
| 10 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
