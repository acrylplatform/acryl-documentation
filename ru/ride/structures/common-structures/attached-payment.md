# AttachedPayment

Структура платежа транзакции вызова скрипта.

## Конструктор

``` ride
AttachedPayment(assetId: ByteVector|Unit, amount: Int)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | assetId | ByteVector&#124;Unit | ID [токена](/blockchain/token.md) |
| 2 | amount | Int | Сумма платежа |
