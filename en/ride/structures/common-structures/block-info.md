# BlockInfo

Structure of a [block](/blockchain/block.md).

## Constructor

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | The [Unix time](https://en.wikipedia.org/wiki/Unix-time) of the creation of a block |
| 2 | height | Int | The [block height](/blockchain/block/block-height.md) |
| 3 | baseTarget | Int | The complexity of the block creation |
| 4 | generationSignature | ByteVector | The signature of a key block |
| 5 | generator | Address | The [address](/blockchain/address.md) of an [/blockchain/account.md) account that created a block |
| 6 | generatorPublicKey | ByteVector | The public key of the account that created a block |
