# Transfer

Structure of a [mass transfer transaction](/blockchain/transaction-type/mass-transfer-transaction.md) token transfer.

## Constructor

``` ride
Transfer(recipient: Address|Alias, amount: Int)
```

## Fields

| # | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | The [address](/blockchain/address.md) of a recipient of tokens |
| 2 | amount | Int | Number of tokens |
