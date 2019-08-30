# Бинарный формат транзакции создания псевдонима

> Узнать больше о [транзакции создания псевдонима](/blockchain/transaction-type/alias-transaction.md)

## Транзакция версии 2

| Порядковый номер поля | Поле | Название JSON-поля | Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Флаг версии |  | Байт | 1 | Указывает что [структура данных](/blockchain/transaction-data-structure.md) транзакции имеет версию 2 или выше.<br>Значение должно быть равно 0 |
| 2 | Тип транзакции | type | Байт  | 1 | ID [типа транзакции](/blockchain/transaction-type.md).<br>Значение должно быть равно 10 |
| 3 | Версия | version | Байт | 1 | Номер версии структуры данных транзакции.<br> Значение должно быть равно 2 |
| 4 | Публичный ключ отправителя | senderPublicKey | Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 5 | Длина псевдонима | | Короткое целое | 2 | Длина псевдонима адреса аккаунта |
| 6 | Псевдоним | alias | Массив байтов | от 4 до 30 | Псевдоним адреса аккаунта |
| 7 | Комиссия | fee | Длинное целое | 8 | Комиссия за транзакцию в [ACRYLETTE](/blockchain/token/acrylette.md) |
| 8 | Временная метка | timestamp | Длинное целое | 8 | Unix-время отправки транзакции в блокчейн |
| 9 | Подтверждения | proofs | Массив [подтверждений](/blockchain/transaction-proof.md) | `S` | Если массив пустой, то `S` = 3. <br> Если массив не пустой, то `S`   = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), <br>где <br>`N` — количество подтверждений в массиве,<br> `P`<sub>n</sub> — размер `N`-го подтверждения в байтах. <br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |
=======
| 1 | Флаг версии |  | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Указывает, что [версия транзакции](/blockchain/transaction/transaction-version.md) является второй или выше.<br>Значение должно быть равно 0 |
| 2 | [ID типа транзакции](/blockchain/transaction-type.md) | type | [Byte](/blockchain/blockchain/blockchain-data-types.md)  | 1 | Значение должно быть равно 10 |
| 3 | [Версия транзакции](/blockchain/transaction/transaction-version.md) | version | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Значение должно быть равно 2 |
| 4 | Открытый ключ аккаунта отправителя транзакции | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 5 | Длина [псевдонима](/blockchain/alias.md) | | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | Количество символов в имени псевдонима |
| 6 | Псевдоним | alias | [String](/blockchain/blockchain/blockchain-data-types.md) | от 4 до 30 |  |
| 7 | [Комиссия за транзакцию](/blockchain/transaction/transaction-fee.md) | fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 8 | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 9 | [Подтверждения транзакции](/blockchain/transaction/transaction-proof.md) | proofs | [Подтверждения](/blockchain/transaction/transaction-proof.md) | `S` | Если массив пустой, то `S` = 3. <br> Если массив не пустой, то `S`   = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), <br>где <br>`N` — количество подтверждений в массиве,<br> `P`<sub>n</sub> — размер `N`-го подтверждения в байтах. <br> Максимальное количество подтверждений в массиве — 8. Максимальный размер каждого подтверждения — 64 байта |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a

## JSON-представление транзакции

Смотрите [пример](https://nodes.wavesplatform.com/transactions/info/5CZV9RouJs7uaRkZY741WDy9zV69npX1FTZqxo5fsryL) в Node API.

## Бинарный формат версии 1

| Порядковый номер поля | Поле | Тип поля | Размер поля в байтах | Комментарий |
| :--- | :--- | :--- | :--- | :--- |
<<<<<<< HEAD
| 1 | Тип транзакции | Байт  | 1 | ID типа транзакции.<br>Значение должно быть равно 6 |
| 2 | Публичный ключ отправителя | Массив байтов | 32 | Публичный ключ аккаунта отправителя |
| 3 | Длина псевдонима  | Короткое целое | 2 | Длина псевдонима адреса аккаунта |
| 4 | Псевдоним | Массив байтов | от 4 до 30 | Псевдоним адреса аккаунта |
| 5 | Комиссия | Длинное целое | 8 | Комиссия за транзакцию в ACRYLETTE |
| 6 | Временная метка | Длинное целое | 8 | Unix-время отправки транзакции в блокчейн |
| 7 | Подпись | Массив байтов | 64 | [Подпись транзакции](/blockchain/transaction-signature.md) |
=======
| 1 | [ID типа транзакции](/blockchain/transaction-type.md) | [Byte](/blockchain/blockchain/blockchain-data-types.md)  | 1 | Значение должно быть равно 6 |
| 2 | Открытый ключ аккаунта отправителя транзакции | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 |  |
| 3 | Длина [псевдонима](/blockchain/alias.md) | [Short](/blockchain/blockchain/blockchain-data-types.md) | 2 | Количество символов в имени псевдонима |
| 4 | Псевдоним | [String](/blockchain/blockchain/blockchain-data-types.md) | от 4 до 30 |  |
| 5 | [Комиссия за транзакцию](/blockchain/transaction/transaction-fee.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 6 | [Временная метка транзакции](/blockchain/transaction/transaction-timestamp.md) | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 |  |
| 7 | [Подпись транзакции](/blockchain/transaction/transaction-signature.md) | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 64 |  |
>>>>>>> 31e41b6d9847032af4f7b5210302f9803949507a
