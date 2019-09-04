# Order

Структура ордера.

### Конструктор

``` ride
Order(id: ByteVector, matcherPublicKey: ByteVector, assetPair: AssetPair, orderType: Buy|Sell, price: Int, amount: Int, timestamp: Int, expiration: Int, matcherFee: Int, matcherFeeAssetId: ByteVector|Unit, sender: Address, senderPublicKey: ByteVector, bodyBytes: ByteVector, proofs: List[ByteVector])
```

### Поля

| # | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | id | ByteVector | ID ордера |
| 2 | matcherPublicKey | ByteVector | Публичный ключ аккаунта матчера |
| 3 | assetPair | AssetPair | Пара токенов |
| 4 | orderType | Buy&#124;Sell | Тип ордера — продажа или покупка |
| 5 | price | Int | Цена обмениваемого токена |
| 6 | amount | Int | Количество обмениваемых токенов |
| 7 | timestamp | Int | [Unix-время](https://ru.wikipedia.org/wiki/Unix-время) валидации ордера матчером |
| 8 | expiration | Int | Unix-время, когда невыполненный ордер будет отменен |
| 9 | matcherFee | Int | Комиссия за исполнение ордера |
| 10 | matcherFeeAssetId | ByteVector&#124;Unit | Токен [комиссии за транзакцию](/blockchain/transaction-fee.md). В настоящее время возможен только ACRYL |
| 11 | sender | Address | [Адрес](/blockchain/address.md) отправителя ордера |
| 12 | senderPublicKey | ByteVector | Публичный ключ аккаунта отправителя ордера |
| 13 | bodyBytes | ByteVector | Массив байтов ордера |
| 14 | proofs | List[ByteVector] | Массив [подтверждений](/blockchain/transaction-proof.md) |
