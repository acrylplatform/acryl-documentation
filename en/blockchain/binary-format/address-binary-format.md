# Address binary format

| # | Field name | Field type | Filed size in bytes |
| --- | :---: | :---: | --- |
| 1 | Version(0x01) | Byte | 1 |
| 2 | Address scheme (0x54 for Testnet and 0x57for Mainnet) | Byte | 1 |
| 3 | Public key hash | Bytes | 20 |
| 4 | Checksum | Bytes | 4 |

`Public key hash` is first 20 bytes of SecureHash of public key bytes.

`Checksum` is first 4 bytes of SecureHash of version, scheme and hash bytes.

`SecureHash` is hash function Keccak256(Blake2b256(data)).
