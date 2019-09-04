# MassTransferTransaction

Structure of a [mass transfer transaction](/blockchain/transaction-type/mass-transfer-transaction.md).

## Constructor

``` ride
MassTransferTransaction(feeAssetId: ByteVector|Unit, assetId: ByteVector|Unit, totalAmount: Int, transfers: List[Transfer], transferCount: Int, attachment: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | feeAssetId | ByteVector&#124;Unit | [Token](/blockchain/token.md) to pay the commission. Currently it can be [ACRYL](/blockchain/token/acryl.md) only |
| 2 | assetId | ByteVector&#124;Unit | ID of a token |
| 3 | totalAmount | Int | Total amount of tokens for mass transfer |
| 4 | transfers | List[Transfer] | Set of token transfers within current transaction |
| 5 | transferCount | Int | Token transfers amount |
| 6 | attachment | ByteVector | Arbitrary data attached to transfer |
| 7 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 8 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 9 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 10 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 11 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 12 | senderPublicKey | ByteVector | Account public key of a sender |
| 13 | bodyBytes | ByteVector | Transaction's array of bytes |
| 14 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
