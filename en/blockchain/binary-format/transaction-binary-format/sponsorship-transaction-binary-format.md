# Sponsorship transaction binary format

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 14\) | 1
| 3 | Version | Byte | 1
| 4 | Transaction type | Byte | 1
| 5 | Version | Byte | 1
| 6 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 7 | Asset ID | ByteStr \(Array[Byte]\) | 32
| 8 | Minimal fee in assets\* | Long | 8
| 9 | Fee | Long | 8
| 10 | Timestamp | Long | 8
| 11 | Proofs | Proofs | See Proofs structure

\* Zero value assume canceling sponsorship.

**Note.** [**Here**](/acryl-environment/acryl-protocol/sponsored-fee.md) you can find more details about Sponsored Transaction.

Below is a sample **Sponsored transaction** encoded as **JSON**:

```cpp
{
  "type" : 14,
  "id" : "CwHecsEjYemKR7wqRkgkZxGrb5UEfD8yvZpFF5wXm2Su",
  "sender" : "3FjTpAg1VbmxSH39YWnfFukAUhxMqmKqTEZ",
  "senderPublicKey" : "5AzfA9UfpWVYiwFwvdr77k6LWupSTGLb14b24oVdEpMM",
  "minSponsoredAssetFee": 100000,
  "fee" : 100000000,
  "timestamp" : 1520945679531,
  "proofs" : [ "4huvVwtbALH9W2RQSF5h1XG6PFYLA6nvcAEgv79nVLW7myCysWST6t4wsCqhLCSGoc5zeLxG6MEHpcnB6DPy3XWr" ],
  "version" : 1,
  "height" : 303
}
```
