# SetScriptTransaction

Structure of a [set script transaction](/blockchain/transaction-type/set-script-transaction.md).

## Constructor

``` ride
SetScriptTransaction(script: ByteVector|Unit, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | script | ByteVector&#124;Unit | Script that must be set for the [account](/blockchain/account.md) |
| 2 | id | ByteVector | [Transaction ID](/blockchain/transaction/transaction-id.md) |
| 3 | fee | Int | [Transaction fee](/blockchain/transaction-fee.md) |
| 4 | timestamp | Int | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) |
| 5 | version | Int | Version of the [data structure](/blockchain/binary-format/transaction-binary-format.md) of a transaction |
| 6 | sender | Address | [Address](/blockchain/address.md) of a transaction sender |
| 7 | senderPublicKey | ByteVector | Account public key of a sender |
| 8 | bodyBytes | ByteVector | Transaction's array of bytes |
| 9 | proofs | List[ByteVector] | Array of [proofs](/blockchain/transaction-proof.md) |
