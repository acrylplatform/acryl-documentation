# Order

Structure of an [order](/blockchain/binary-format/order-binary-format.md).

## Constructor

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | The ID of an order |
| 2 | matcherPublicKey | ByteVector | The public key of a matcher |
| 3 | assetPair | AssetPair | The pair of [tokens](/blockchain/token.md) |
| 4 | orderType | Buy&#124;Sell | The type of an order — selling or buying |
| 5 | price | Int | The price of a token to exchange |
| 6 | amount | Int | The number of tokens to exchange |
| 7 | timestamp | Int | The [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the validation of an order by a matcher  |
| 8 | expiration | Int | The Unix time when an uncompleted order will be cancelled |
| 9 | matcherFee | Int | The [transaction fee](/blockchain/transaction-fee.md) |
| 10 | matcherFeeAssetId | ByteVector&#124;Unit | The token of a transaction fee.<br>It can only be [ACRYL](/blockchain/token/acryl.md) |
| 11 | sender | Address | The [address](/blockchain/address.md) of the sender of an order |
| 12 | senderPublicKey | ByteVector | The public key of the sender of an order |
| 13 | bodyBytes | ByteVector | The array of bytes of an order |
| 14 | proofs | List[ByteVector] | The array of [proofs](/blockchain/transaction-proof.md) |
