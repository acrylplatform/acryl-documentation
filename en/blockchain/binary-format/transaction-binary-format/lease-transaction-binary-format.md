# Lease transaction binary format

## Binary format version 1

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 8\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3 | Recipient | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 4 | Amount | Long | 8
| 5 | Fee | Long | 8
| 6 | Timestamp | Long | 8
| 7 | Signature | ByteStr \(Array[Byte]\) | 64

The transaction's signature is calculated from the following bytes:

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 8\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3 | Recipient | Address or Alias | Depends on the first byte \(1 - Address, 2 - Alias\)
| 4 | Amount | Long | 8 |
| 5 | Fee | Long | 8 |
| 6 | Timestamp | Long | 8 |

## Binary format version 2

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte (constant, value = 0) | 1
| 2 | Transaction type | Byte (constant, value = 8) | 1
| 3 | Version | Byte | 1
| 4 | Reserved field | Byte (constant, value = 0)| 1
| 5 | Sender's public key | PublicKey (Array[Byte]) | 32
| 6 | Recipient | Address or Alias | Depends on the first byte (1 - Address, 2 - Alias)
| 7 | Amount | Long | 8
| 8 | Fee | Long | 8
| 9 | Timestamp | Long | 8
| 10 | Proofs | Proofs | See Proofs structure

\* Only Acryl are currently supported
