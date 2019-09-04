# Invocation

Structure of the abbreviated representation of an [invoke script transaction](/blockchain/transaction-type/invoke-script-transaction.md).

## Constructor

``` ride
Invocation(caller: Address, callerPublicKey: ByteVector, payment: AttachedPayment|Unit, transactionId: ByteVector, fee: Int, feeAssetId: ByteVector|Unit)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | caller | Address | The address of an [account](/blockchain/account.md) that sent a transaction |
| 2 | callerPublicKey | ByteVector | The public key of an account that sent a transaction |
| 3 | payment | AttachedPayment&#124;Unit | The attached payment |
| 4 | transactionId | ByteVector | The ID of a transaction |
| 5 | fee | Int | The transaction fee |
| 6 | feeAssetId | ByteVector&#124;Unit | The [token](/blockchain/token.md) of a transaction fee |
