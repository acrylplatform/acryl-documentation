# Issue transaction binary format

## Binary format version 1

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 3\) | 1
| 2 | Signature | ByteStr \(Array[Byte]\) | 64
| 3 | Transaction type | Byte \(constant, value = 3\) | 1
| 4 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 5.1 | Asset name length \(N\) |  | 2
| 5.2 | Asset name | Array[Byte] | 4 <= N <= 16
| 6.1 | Description length \(D\) |  | 2
| 6.2 | Description | Array[Byte] | D <= 1000
| 7 | Quantity | Long | 8
| 8 | Decimals | Byte | 1
| 9 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 10 | Fee | Long | 8
| 11 | Timestamp | Long | 8

The transaction's signature is calculated from the following bytes:

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction type | Byte \(constant, value = 3\) | 1
| 2 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 3.1 | Asset name length \(N\) |  | 2
| 3.2 | Asset name | Array[Byte] | 4 <= N <= 16
| 4.1 | Description length \(D\) |  | 2
| 4.2 | Description | Array[Byte] | D <= 1000
| 5 | Quantity | Long | 8 |
| 6 | Decimals | Byte | 1 |
| 7 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 8 | Fee | Long | 8 |
| 9 | Timestamp | Long | 8 |

## Binary format version 2

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Transaction multiple version mark | Byte \(constant, value = 0\) | 1
| 2 | Transaction type | Byte \(constant, value = 3\) | 1
| 3 | Version | Byte | 1
| 4 | Chain ID | Byte | 1
| 5 | Sender's public key | PublicKey \(Array[Byte]\) | 32
| 6.1 | Name length \(N\) |  | 2
| 6.2 | Name | Array[Byte] | 4 <= N <= 16
| 7.1 | Description length \(D\) |  | 2
| 7.2 | Description | Array[Byte] | D <= 1000
| 8 | Quantity | Long | 8
| 9 | Decimals | Byte | 1
| 10 | Reissuable flag \(1 - True, 0 - False\) | Boolean | 1
| 11 | Fee | Long | 8
| 12 | Timestamp | Long | 8
| 13.1 | Script existence flag \(1/0\) |  | 1
| 13.2 | Script length \(S\) |  | 2 or 0 \(depends on the byte in 13.1\)
| 13.3 | Script | Script | S <= 32768 or 0 \(depends on the byte in 13.1\)
| 14 | Proofs | Proofs | See Proofs structure
