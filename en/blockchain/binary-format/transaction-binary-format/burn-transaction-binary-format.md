# Burn transaction binary format

> Learn more about [burn transaction](/blockchain/transaction-type/burn-transaction.md)

## Transaction version 2

| Field order number | Field | JSON field name | Field type | Field size in bytes | Comment |
| :--- | :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Version flag | | Byte | 1 | Indicates that this is a transaction with a [data structure](/blockchain/transaction-data-structure.md) of version 2 or above. <br>The value has to be equal to 0 |
| 2 | Transaction type | type | Byte | 1 | ID of the [transaction type](/blockchain/transaction-type.md). <br>The value has to be equal to 6 |
| 3 | Version number | version | Byte | 1 | Version number of the data structure of the transaction.  <br>The value has to be equal to 2 |
| 4 | Network ID | chainId|Byte | 1 | Determines the network where the transaction will be published to. <br>84 for [test network](/blockchain/blockchain-network/test-network.md), 87 for [mainnet](/blockchain/blockchain-network/main-network.md) |
| 5 | Public key of sender | senderPublicKey | Array of bytes | 32 | Account public key of the sender |
| 6 | Token ID | assetId| Array of bytes | 32 | ID of the token to burn |
| 7 | Amount | amount | Long | 8 | Amount of tokens to burn |
| 8 | Fee | fee | Long | 8 | [Transaction fee](/blockchain/transaction-fee.md) in [ACRYLETTEs](/blockchain/token/acrylette.md) |
| 9 | Timestamp | timestamp | Long | 8 | Unix time of sending a transaction to the blockchain |
| 10 | Proofs | proofs | Array of [proofs](/blockchain/transaction-proof.md) | `S` | If the array is empty, then `S`= 3. <br>If the array is not empty, then `S` = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), where `N` is the number of proofs in the array, `P`<sub>n</sub> is the size on `N`-th proof in bytes. <br>The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |
=======
| 1 | Version flag | | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Indicates the [transaction version](/blockchain/transaction/transaction-version.md) is version 2 or higher.<br>Value must be 0 |
| 2 | [Transaction type ID](/blockchain/transaction-type.md) | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Value must be 6 |
| 3 | [Transaction version](/blockchain/transaction/transaction-version.md) | version | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Value must be 2 |
| 4 | [Chain ID](/blockchain/blockchain-network/chain-id.md) | chainId | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | 84 for [test network](/blockchain/blockchain-network/test-network.md), 87 for [main network](/blockchain/blockchain-network/main-network.md) |
| 5 | Public key of the transaction sender | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 6 | [ID](/blockchain/token/token-id.md) of the token to burn | assetId| Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 7 | Amount of tokens to burn | amount | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 8 | [Transaction fee](/blockchain/transaction/transaction-fee.md) | fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 9 | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 10 | [Transaction proofs](/blockchain/transaction/transaction-proof.md) | proofs | [Proofs](/blockchain/transaction/transaction-proof.md) | `S` | If the array is empty, then `S`= 3. <br>If the array is not empty, then `S` = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), where `N` is the number of proofs in the array, `P`<sub>n</sub> is the size on `N`-th proof in bytes. <br>The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a

## JSON representation of the transaction

See the [example](https://nodes.wavesplatform.com/transactions/info/csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL) in Node API.

## Transaction version 1

| Field order number | Field | Field type | Field size in bytes | Comment |
| :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Transaction type | Byte | 1 | ID of the transaction type.The value has to be equal to 6 |
| 2 | Sender's public key | Array of bytes | 32 | Public key of the sender's account |
| 3 | Token ID | Array of bytes | 32 | ID of the token to burn |
| 4 | Amount | Long | 8 | Amount of tokens to burn |
| 5 | Fee | Long | 8 | Transaction fee in ACRYLETTE |
| 6 | Timestamp | Long | 8 | Unix time of sending a transaction to the blockchain |
| 7 | Signature | Array of bytes | 64 | [Transaction signature](/blockchain/transaction-signature.md) |
=======
| 1 | [Transaction type ID](/blockchain/transaction-type.md) | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Value must be 6 |
| 2 | Public key of the transaction sender | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 3 | [ID](/blockchain/token/token-id.md) of the token to burn | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 4 | Amount of tokens to burn | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 5 | [Transaction fee](/blockchain/transaction/transaction-fee.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 6 | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 7 | [Transaction signature](/blockchain/transaction/transaction-signature.md) | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 |  |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a
