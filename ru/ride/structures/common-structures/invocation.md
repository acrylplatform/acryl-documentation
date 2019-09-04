# Invocation

Структура сокращенного представления [транзакции вызова скрипта](/blockchain/transaction-type/invoke-script-transaction.md).

## Конструктор

``` ride
Invocation(caller: Address, callerPublicKey: ByteVector, payment: AttachedPayment|Unit, transactionId: ByteVector, fee: Int, feeAssetId: ByteVector|Unit)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | caller | Address | [Адрес](/blockchain/address.md) аккаунта, который отправил транзакцию |
| 2 | callerPublicKey | ByteVector | Публичный ключ аккаунта, который отправил транзакцию |
| 3 | payment | AttachedPayment&#124;Unit | Приложенный платеж |
| 4 | transactionId | ByteVector | ID транзакции |
| 5 | fee | Int | [Комиссия за транзакцию](/blockchain/transaction-fee.md) |
| 6 | feeAssetId | ByteVector&#124;Unit | [Токен](/blockchain/token.md) комиссии за отправку транзакции |
