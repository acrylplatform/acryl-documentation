# Transfer transaction binary format

## Binary format version 1

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 4\) | 1
| 2 | Signature | ByteStr \(Array[Byte]\) | 64
| 3 | Transaction type | Byte \(constant, value = 4\) | 1
| 4 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 5.1 | Asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 5.2 | Asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 5.1\)
| 6.1 | Fee's asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 6.2 | Fee's asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 6.1\)
| 7 | Timestamp | Long | 8
| 8 | Amount | Long | 8
| 9 | Fee | Long | 8
| 10 | Recipient | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 11.1 | Attachment length \(N\) |  | 2
| 11.2 | Attachment | Array[Byte] | N <= 140

The transaction's signature is calculated from the following bytes:

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 4\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3.1 | Asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 3.2 | Asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 3.1\)
| 4.1 | Fee's asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 4.2 | Fee's asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 4.1\)
| 5 | Timestamp | Long | 8 |
| 6 | Amount | Long | 8 |
| 7 | Fee | Long | 8 |
| 8 | Recipient | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 9.1 | Attachment length \(N\) |  | 2
| 9.2 | Attachment | Array[Byte] | N <= 140

## Binary format version 2

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 4\) | 1
| 3 | Version | Byte | 1
| 4 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 5.1 | Asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 5.2 | Asset ID\* | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 5.1\)
| 6.1 | Fee's asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 6.2 | Fee's asset ID | AssetId \(ByteStr = Array[Byte]\) | 32 or 0 \(depends on the byte in 6.1\)
| 7 | Timestamp | Long | 8
| 8 | Amount | Long | 8
| 9 | Fee | Long | 8
| 10 | Recipient | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 11.1 | Attachment length \(N\) |  | 2
| 11.2 | Attachment | Array[Byte] | N <= 140
| 12 | Proofs | Proofs | See Proofs structure

* The fee only in Acryl;
* You may sign your transaction in your way and place the signature in proofs.
