# Бинарный формат транзакции сжигания токена

> Узнать больше о [транзакции сжигания токена](/blockchain/transaction-type/burn-transaction.md)

## Транзакция версии 2

| Порядковый номер поля | Поле | Название JSON-поля |Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Флаг версии | | Байт | 1 | Указывает что [структура данных](/blockchain/transaction-data-structure.md) транзакции имеет версию 2 или выше. <br>Значение должно быть равно 0 |
| 2 | Тип транзакции |type| Байт | 1 | ID [типа транзакции](/blockchain/transaction-type.md). <br>Значение должно быть равно 6 |
| 3 | Номер версии |version| Байт | 1 | Номер версии структуры данных транзакции. <br>Значение должно быть равно 2 |
| 4 | ID сети |chainId| Байт | 1 | Задает сеть, в которой транзакция будет опубликована. <br>84 для тестовой сети, 87 для основной сети |
| 5 | Публичный ключ отправителя |senderPublicKey| Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 6 | ID токена |assetId| Массив байтов | 32 | ID сжигаемого токена |
| 7 | Количество токенов |amount| Длинное целое | 8 | Количество сжигаемых токенов |
| 8 | Комиссия|fee | Длинное целое | 8 | Комиссия за транзакцию в [ACRYLETTE](/blockchain/token/acrylette.md) |
| 9 | Временная метка|timestamp | Длинное целое | 8 | Unix-время отправки транзакции в блокчейн |
| 10 | Подтверждения |proofs| Массив [подтверждений](/blockchain/transaction-proof.md) | `S` | Если массив пустой, то `S`= 3. <br>Если массив не пустой, то `S`= 3 + 2 × `N` + \(`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>\), <br>где <br>`N` — количество подтверждений в массиве, <br>`P`<sub>n</sub> — размер `N`-го подтверждения в байтах.<br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |
=======
| 1 | Флаг версии | | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Указывает, что [версия транзакции](/blockchain/transaction/transaction-version.md) является второй или выше.<br>Значение должно быть равно 0 |
| 2 | [ID типа транзакции](/blockchain/transaction-type.md) |type| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 6 |
| 3 | [Версия транзакции](/blockchain/transaction/transaction-version.md) |version| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 2 |
| 4 | [Байт сети](/blockchain/blockchain-network/chain-id.md) |chainId| [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | 84 для [тестовой сети](/blockchain/blockchain-network/test-network.md), 87 для [основной сети](/blockchain/blockchain-network/main-network.md) |
| 5 | Открытый ключ аккаунта отправителя транзакции |senderPublicKey| Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 6 | [ID](/blockchain/token/token-id.md) сжигаемого токена |assetId| Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 7 | Количество сжигаемых токенов |amount| [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 8 | [Комиссия за транзакцию](/blockchain/transaction/transaction-fee.md) |fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 9 | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) |timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 10 | [Подтверждения транзакции](/blockchain/transaction/transaction-proof.md) |proofs| [Подтверждения](/blockchain/transaction/transaction-proof.md) | `S` | Если массив пустой, то `S`= 3. <br>Если массив не пустой, то `S`= 3 + 2 × `N` + \(`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>\), <br>где <br>`N` — количество подтверждений в массиве, <br>`P`<sub>n</sub> — размер `N`-го подтверждения в байтах.<br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a

## JSON-представление транзакции

Смотрите [пример](https://nodes.wavesplatform.com/transactions/info/csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL) в Node API.

## Бинарный формат версии 1

| Порядковый номер поля | Поле | Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Тип транзакции | Байт | 1 | ID типа транзакции. <br>Значение должно быть равно 6 |
| 2 | Публичный ключ отправителя | Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 3 | ID токена  | Массив байтов | 32 | ID сжигаемого токена |
| 4 | Количество токенов | Длинное целое | 8 | Количество сжигаемых токенов  |
| 5 | Комиссия | Длинное целое | 8 | Комиссия за транзакцию в ACRYLETTE |
| 6 | Временная метка | Длинное целое | 8 | Unix-время публикации транзакции в сеть |
| 7 | Подпись | Массив байтов | 64 | [Подпись транзакции](/blockchain/transaction-signature.md) |
=======
| 1 | [ID типа транзакции](/blockchain/transaction-type.md) | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 6 |
| 2 | Открытый ключ аккаунта отправителя транзакции | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 3 | [ID](/blockchain/token/token-id.md) сжигаемого токена  | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 4 | Количество сжигаемых токенов | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 5 | [Комиссия за транзакцию](/blockchain/transaction/transaction-fee.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 6 | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 7 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 |  |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a
