# ScriptTransfer

Структура перевода [токенов](/blockchain/token.md).

### Конструктор

``` ride
ScriptTransfer(recipient: Address|Alias, amount: Int, asset: ByteVector|Unit)
```

### Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | recipient | Address&#124;Alias | [Адрес](/blockchain/address.md) или [псевдоним](/blockchain/alias.md) получателя токенов |
| 2 | amount | Int | Количество токенов |
| 3 | asset | ByteVector&#124;Unit | ID токена |
