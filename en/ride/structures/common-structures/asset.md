# Asset

Structure of a [token](/blockchain/token.md).

## Constructor

``` ride
Asset(id: ByteVector, quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

## Fields

|   #   | Name | Data type | Description |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | Token ID[/blockchain/token.md] |
| 2 | quantity | Int | Amount of issued token |
| 3 | decimals | Int | Number of decimal places |
| 4 | issuer | Address | [Address](/blockchain/address.md) of the [account](/blockchain/account.md) that issued a token |
| 5 | issuerPublicKey | ByteVector | Public key of the account that issued a token |
| 6 | reissuable | Boolean | true — token can be reissued, false — cannot be reissued |
| 7 | scripted | Boolean | true — [smart asset](/ride/smart-assets.md), false — regular token |
| 8 | sponsored | Boolean | true — token can be sponsored, false — cannot be sponsored |
