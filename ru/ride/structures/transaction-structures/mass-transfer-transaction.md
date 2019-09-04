# MassTransferTransaction

Структура [транзакции массового перевода](/blockchain/transaction-type/mass-transfer-transaction.md).

## Конструктор

``` ride
MassTransferTransaction(feeAssetId: ByteVector|Unit, assetId: ByteVector|Unit, totalAmount: Int, transfers: List[Transfer], transferCount: Int, attachment: ByteVector, id: ByteVector, fee: Int, timestamp: Int, version: Int, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

## Поля структуры

| # | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | feeAssetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | [Токен](/blockchain/token.md) комиссии. В настоящее разрешен только [ACRYL](/blockchain/token/acryl.md) |
| 2 | assetId | [ByteVector](/ride/data-types/byte-vector.md)&#124;[Unit](/ride/data-types/unit.md) | ID токена |
| 3 | totalAmount | [Int](/ride/data-types/int.md) | Общая сумма токена для массового перевода |
| 4 | transfers | [List](/ride/data-types/list.md)[[Transfer](/ride/structures/common-structures/transfer.md)] | Список переводов токена в рамках текущей транзакции |
| 5 | transferCount | [Int](/ride/data-types/int.md) | Количество переводов токена |
| 6 | attachment | [ByteVector](/ride/data-types/byte-vector.md) | Произвольные данные, которые могут быть прикреплены к переводу |
| 7 | id | [ByteVector](/ride/data-types/byte-vector.md) | [ID транзакции](/blockchain/transaction/transaction-id.md) |
| 8 | fee | [Int](/ride/data-types/int.md) | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 9 | timestamp | [Int](/ride/data-types/int.md) | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) |
| 10 | version | [Int](/ride/data-types/int.md) | Версия [структуры данных](/blockchain/transaction-data-structure.md) транзакции |
| 11 | sender | [Address](/ride/structures/common-structures/address.md) | [Адрес](/blockchain/address.md) отправителя транзакции |
| 12 | senderPublicKey | [ByteVector](/ride/data-types/byte-vector.md) | Публичный ключ отправителя транзакции |
| 13 | bodyBytes | [ByteVector](/ride/data-types/byte-vector.md) | [Байты тела транзакции](/blockchain/transaction/transaction-body-bytes.md) |
| 14 | proofs | [List](/ride/data-types/list.md)[[ByteVector](/ride/data-types/byte-vector.md)] | Список [подтверждений](/blockchain/transaction-proof.md) |
