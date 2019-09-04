# ScriptTrnasfer

Structure of a [token](/blockchain/token.md) transfer.

### Constructor

``` ride
ScriptTransfer(recipient: Address|Alias, amount: Int, asset: ByteVector|Unit)
```

### Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | The [address](/blockchain/address.md) or the [alias](/blockchain/alias.md) of a recipient of tokens |
| 2 | amount | Int | The number of tokens |
| 3 | asset | ByteVector&#124;Unit | The ID of a token |
