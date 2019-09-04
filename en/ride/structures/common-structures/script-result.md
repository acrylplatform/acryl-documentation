# ScriptResult

Structure of the execution result of a callable function.

## Constructor

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | The list of records of an [account data storage](/blockchain/transaction-proof.md) |
| 2 | transferSet | TransferSet | The list of [tokens](/blockchain/token.md) of a transfer |
