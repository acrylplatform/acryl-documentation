# InvokeScriptTransaction

Structure of an [invoke script transaction](/blockchain/transaction-type/invoke-script-transaction.md).

### Constructor

``` ride
InvokeScriptTransaction(dapp: Address|Alias, payment: AttachedPayment|Unit, feeAssetId: ByteVector|Unit, function: String, args: List[Boolean|ByteVector|Int|String], id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | dapp | [Address](/ride/structures/common-structures/address.md)&#124;[Alias](/ride/structures/common-structures/alias.md) | [Address](/blockchain/address.md) or [alias](/blockchain/alias.md) of the [account]((/blockchain/account.md)) which is calling a function |
| 2 | payment | [AttachedPayment](/ride/structures/common-structures/attached-payment.md)&#124;[Unit](/ride/data-types/unit.md) | Payment attached to the [transaction](/blockchain/transaction.md) |
| 3 | feeAssetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | [Token](/blockchain/token.md) to pay the commission. Currently, it can be only in [ACRYL](/blockchain/token/acryl.md) |
| 4 | function | [String](/ride/data-types/string.md) | [Function](/ride/functions.md) name |
| 5 | args | [List](/ride/data-types/list.md)[[Boolean](/ride/data-types/boolean.md)&#124;[ByteVector](/ride/data-types/byte-vector.md)&#124;[Int](/ride/data-types/int.md)&#124;[String](/ride/data-types/string.md)] | [Function](/ride/functions.md) parameters |
| 6 | id | [ByteVector](/ride/data-types/byte-vector.md) | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 7 | fee | [Int](/ride/data-types/int.md) | [Transaction fee](/blockchain/transaction-fee.md) |
| 8 | timestamp | [Int](/ride/data-types/int.md) | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 9 | version | [Int](/ride/data-types/int.md) | Version of the [transaction binary format](/blockchain/binary-format/transaction-binary-format.md) |
| 10 | sender | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of the transaction sender |
| 11 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Account public key of the transaction sender |
| 12 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | Transaction's array of bytes |
| 13 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Array of [proofs](/blockchain/transaction-proof.md) |
