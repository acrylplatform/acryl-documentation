# Invoke script transaction binary format

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte (constant, value = 0) | 1
| 2 | Transaction type | Byte (constant, value = 16) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey (Array[Byte]) | 32
| 6 | Contract address | Address | 26
| 7 | Function call | EXPR | F
| 8.1 | Payments size |  | 2
| 8.2 | Payment 1 length (P1) |  | 2 or 0 (depends on the short in 8.1)
| 8.3 | Payment 1 | Payment (Long, Option[AssetId]) | P1 <= 40 or 0 (depends on the short in 8.1)
| ... | ... | ... | ... |
| 9 | Fee | Long | 8
| 10.1 | Fee's asset ID flag \(1 - asset, 0 - Acryl\) |  | 1
| 10.2 | Fee's asset ID | AssetId (ByteStr = Array[Byte]) | 32 or 0 (depends on the byte in 10.1)
| 11 | Timestamp | Long | 8
| 12 | Proofs | Proofs | See Proofs structure
