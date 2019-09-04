# Alias binary format

| # | Field name | Type | Length in Bytes |
| --- | --- | --- | --- |
| 1 | Version (0x02) | Byte | 1 |
| 2 | Address scheme (0x54 for Testnet and 0x57 for Mainnet) | Byte | 1 |
| 3 | Alias bytes length (N) | Int | 2 |
| 4 | Alias bytes | Bytes | 4 <= N <= 30 |

Alias is a UTF-8 string with the following constraints:

* It contains from 4 to 30 UTF-8 characters
* It can contain characters only from the following alphabet: `-.0123456789@_abcdefghijklmnopqrstuvwxyz`
* It cannot contain '\n' or any leading/trailing whitespaces
