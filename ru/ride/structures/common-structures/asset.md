# Asset

Структура [токена](/blockchain/token.md).

## Конструктор

``` ride
Asset(quantity: Int, decimals: Int, issuer: Address, issuerPublicKey: ByteVector, reissuable: Boolean, scripted: Boolean, sponsored: Boolean)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | quantity | Int | Количество выпущенных [токенов](/blockchain/token.md) |
| 2 | decimals | Int | Число знаков после запятой у токена |
| 3 | issuer | Address | Адрес аккаунта, который выпустил токен |
| 4 | issuerPublicKey | ByteVector | Публичный ключ аккаунта, выпустившего токен |
| 5 | reissuable | Boolean | true — токен можно довыпускать, false — нельзя довыпускать |
| 6 | scripted | Boolean | true — [смарт-ассет](/blockchain/smart-asset.md), false — обычный токен |
| 7 | sponsored | Boolean | true — токен спонсируемый, false — неспонсируемый |
