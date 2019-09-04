# Lease Cancel transaction binary format

## Binary format version 1

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 9\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3 | Fee | Long | 8
| 4 | Timestamp | Long | 8
| 5 | Lease ID | ByteStr \(Array[Byte]\) | 32
| 6 | Signature | ByteStr \(Array[Byte]\) | 64

## Binary format version 2

| \# | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 9\) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 6 | Fee | Long | 8
| 7 | Timestamp | Long | 8
| 8 | Lease ID | ByteStr \(Array[Byte]\) | 32
| 9 | Proofs | Proofs | See Proofs structure
