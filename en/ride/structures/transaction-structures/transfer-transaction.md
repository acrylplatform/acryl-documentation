# TransferTransaction

Structure of a [transfer transaction](/blockchain/transaction-type/transfer-transaction.md).

## Constructor

``` ride
TransferTransaction(feeAssetId: ByteVector|Unit, amount: Int, assetId: ByteVector|Unit, recipient: Address|Alias, attachment: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | feeAssetId | ByteVector&#124;Unit | [Token](/blockchain/token.md) to pay the commission. Currently it can be [ACRYL](/blockchain/token/acryl.md) only |
| 2 | amount | Int | Amount of tokens to transfer |
| 3 | assetId | ByteVector&#124;Unit | ID of a token |
| 4 | recipient | Address&#124;Alias | [Address](/blockchain/address.md) or [alias](/blockchain/alias.md) of the recipient |
| 5 | attachment | ByteVector | Arbitrary data attached to transfer |
| 6 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 7 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 8 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 9 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 10 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 11 | senderPublicKey | ByteVector | Account public key of a sender |
| 12 | bodyBytes | ByteVector | Transaction's array of bytes |
| 13 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
