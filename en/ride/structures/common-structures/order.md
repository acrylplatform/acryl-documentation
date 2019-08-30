# Order

Structure of an [order](/blockchain/binary-format/order-binary-format.md).

## Constructor

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
<<<<<<< HEAD
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
=======
| 1 | id | [ByteVector](/ride/data-types/byte-vector.md) | ID of an order |
| 2 | matcherPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Public key of a matcher |
| 3 | assetPair | [AssetPair](/ride/structures/common-structures/asset-pair.md) | Pair of [tokens](/blockchain/token.md) |
| 4 | orderType | Buy&#124;Sell | Type of an order — selling or buying |
| 5 | price | [Int](/ride/data-types/int.md) | Price of a token to exchange |
| 6 | amount | [Int](/ride/data-types/int.md) | Number of tokens to exchange |
| 7 | timestamp | [Int](/ride/data-types/int.md) | [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the validation of an order by a matcher  |
| 8 | expiration | [Int](/ride/data-types/int.md) | Unix time when an uncompleted order will be cancelled |
| 9 | matcherFee | [Int](/ride/data-types/int.md) | [Transaction fee](/blockchain/transaction/transaction-fee.md) |
| 10 | matcherFeeAssetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | Token of a transaction fee.<br>It can only be [WAVES](/blockchain/token/waves.md) |
| 11 | sender | [Address](/ride/structures/common-structures/address.md) | [Address](/blockchain/address.md) of the sender of an order |
| 12 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Public key of the sender of an order |
| 13 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | Array of bytes of an order |
| 14 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Array of [proofs](/blockchain/transaction/transaction-proof.md) |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a
