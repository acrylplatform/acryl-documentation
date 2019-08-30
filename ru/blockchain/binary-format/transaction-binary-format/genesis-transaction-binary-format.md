# Бинарный формат транзакции генезиса

> Узнать больше о [транзакции генезиса](/blockchain/transaction-type/genesis-transaction.md)

## Транзакция версии 1

| Порядковый номер поля | Поле | Название JSON-поля |Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Тип транзакции |type| Байт | 1 | ID [типа транзакции](/blockchain/transaction-type.md). <br>Значение должно быть равно 6 |
| 2 | Временная метка | timestamp | Длинное целое | 8 | Unix-время отправки транзакции в блокчейн |
| 3 | Адрес аккаунта | recipient | Массив байтов | 26 |  |
| 4 | Количество | amount | Длинное целое | 8 | Количество [ACRYL](/blockchain/token/acryl.md), которое будет начислено аккаунту |
| 5 | Комиссия|fee | Длинное целое | 8 | Комиссия за транзакцию в [ACRYLETTE](/blockchain/token/acrylette.md) |
| 6 | Подпись | signature | Массив байтов | 64 | [Подпись транзакции](/blockchain/transaction-signature.md) |
=======
| 1 | [ID типа транзакции](/blockchain/transaction-type.md) |type| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 1 |
| 2 | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 3 | [Адрес](/blockchain/address.md) получателя | recipient | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 26 |  |
| 4 | Количество [WAVES](/blockchain/token/waves.md), которое будет переведено на [аккаунт](/blockchain/account.md) | amount | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 5 | [Комиссия за транзакцию](/blockchain/transaction/transaction-fee.md) | fee | [Long](/blockchain/blockchain/blockchain-data-types.md)| 8 |  |
| 6 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) | signature | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 |  |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a

## JSON-представление транзакции

Смотрите [пример](https://nodes.wavesplatform.com/transactions/info/2DVtfgXjpMeFf2PQCqvwxAiaGbiDsxDjSdNQkc5JQ74eWxjWFYgwvqzC4dn7iB1AhuM32WxEiVi1SGijsBtYQwn8) в Node API.
