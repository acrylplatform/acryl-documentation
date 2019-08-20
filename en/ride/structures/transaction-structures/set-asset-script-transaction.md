# SetAssetScriptTransaction

Structure of a [set asset script transaction](/blockchain/transaction-type/set-asset-script-transaction.md).

## Constructor

``` ride
SetAssetScriptTransaction(script: ByteVector|Unit, assetId: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | script | ByteVector&#124;Unit | Script that must be set for the [token](/blockchain/token.md) |
| 2 | assetId | ByteVector | ID of a token |
| 3 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 4 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 5 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 6 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 7 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 8 | senderPublicKey | ByteVector | Account public key of a sender |
| 9 | bodyBytes | ByteVector | [Transaction body bytes](/blockchain/transaction/transaction-body-bytes.md) |
| 10 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
