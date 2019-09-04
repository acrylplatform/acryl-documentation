# Новости

## Августовские статьи

### Начало работы

* [Руководство пользователя](getting-started/getting-started-for-users.md)
* [Руководство разработчика](getting-started/getting-started-for-developers.md)

### RIDE

* Встроенные функции
  * [Функции декодирования](ride/functions/built-in-functions/decoding-functions.md)
  * [Функции исключения](ride/functions/built-in-functions/exception-functions.md)
  * [Функции кодирования](ride/functions/built-in-functions/encoding-functions.md)
  * [Функции конвертации](ride/functions/built-in-functions/converting-functions.md)
  * [Функции массива байтов](ride/functions/built-in-functions/byte-array-functions.md)
  * [Функции хеширования](ride/functions/built-in-functions/hashing-functions.md)
* [Выражение](ride/base-concepts/expression.md)
* [Директивы](ride/script/directives.md)
* [Константы](ride/constants.md)
* [Операторы](ride/operators.md)
* [Определение](ride/base-concepts/definition.md)
* [Переменные](ride/variables.md)
* [Функции](ride/functions.md) — [<span style="color:green">обновлено</span>](https://github.com/acrylplatform/acryl-documentation/pull/1465/files)
* Структуры транзакций
  * [DataTransaction](ride/structures/transaction-structures/data-transaction.md)
  * [ExchangeTransaction](ride/structures/transaction-structures/exchange-transaction.md)
  * [GenesisTransaction](ride/structures/transaction-structures/genesis-transaction.md)
  * [InvokeScriptTransaction](ride/structures/transaction-structures/invoke-script-transaction.md)
  * [LeaseTransaction](ride/structures/transaction-structures/lease-transaction.md)
  * [MassTransferTransaction](ride/structures/transaction-structures/mass-transfer-transaction.md)
  * [ReissueTransaction](ride/structures/transaction-structures/reissue-transaction.md)
  * [SetAssetScriptTransaction](ride/structures/transaction-structures/set-asset-script-transaction.md)

### Блокчейн

* Транзакция
  * [ID транзакции](blockchain/transaction/transaction-id.md)
  * [Временна́я метка транзакции](blockchain/transaction/transaction-timestamp.md)
* Тип транзакции
  * [Транзакция данных](blockchain/transaction-type/data-transaction.md) — [<span style="color:green">обновлено</span>](https://github.com/acrylplatform/acryl-documentation/pull/1456/files)
* Узел
  * [Валидирующий узел](blockchain/node/validating-node.md)

## Acryl Node

* [Установка gRPC Server](acryl-node/extensions/grpc-server/grpc-server-installation.md)

## Июльские статьи

### Блокчейн

* [Байты тела транзакции](blockchain/transaction/transaction-body-bytes.md)
* [Бинарный формат](blockchain/binary-format.md)
* [Бинарный формат транзакции](blockchain/binary-format/transaction-binary-format.md)
* Блок
  * [Блок генезиса](blockchain/block/genesis-block.md)
  * [Генерация блока](blockchain/block/block-generation.md)
    * [Базовая цель](blockchain/block/block-generation/base-target.md)
  * [Подпись блока](blockchain/block/block-signature.md)
* [Комиссия матчера](blockchain/matcher-fee.md)
* [Лизинг](blockchain/leasing.md)
* [Майнинг](blockchain/mining.md)
  * [Майнер](blockchain/mining/miner.md)
  * [Майнящий аккаунт](blockchain/mining/mining-account.md)
* [Ордер](blockchain/order.md)
* [Сеть блокчейна](blockchain/blockchain-network.md)
* Тип транзакции
  * [Транзакция вызова скрипта](blockchain/transaction-type/invoke-script-transaction.md)
  * [Транзакция выпуска](blockchain/transaction-type/issue-transaction.md)
  * [Транзакция довыпуска](blockchain/transaction-type/reissue-transaction.md)
  * [Транзакция закрытия лизинга](blockchain/transaction-type/lease-cancel-transaction.md)
  * [Транзакция массового перевода](blockchain/transaction-type/mass-transfer-transaction.md)
  * [Транзакция обмена](blockchain/transaction-type/exchange-transaction.md)
  * [Транзакция перевода](blockchain/transaction-type/transfer-transaction.md)
  * [Транзакция установки скрипта](blockchain/transaction-type/set-script-transaction.md)
  * [Транзакция установки скрипта ассета](blockchain/transaction-type/set-asset-script-transaction.md)
* Узел
  * [Майнящий узел](blockchain/node/mining-node.md)

### Acryl Node

* Расширения
  * [gRPC Server](acryl-node/extensions/grpc-server.md)
    * [Установка gRPC Server](acryl-node/extensions/grpc-server/grpc-server-installation.md)
  * [Матчер](acryl-node/extensions/matcher.md)

### RIDE

* [Аннотации](ride/functions/annotations.md)
* Структуры
  * [Общие структуры](ride/structures/common-structures.md)
    * [Address](ride/structures/common-structures/address.md)
    * [Asset](ride/structures/common-structures/asset.md)
    * [AssetPair](ride/structures/common-structures/asset-pair.md)
    * [AttachedPayment](ride/structures/common-structures/attached-payment.md)
    * [BlockInfo](ride/structures/common-structures/block-info.md)
    * [DataEntry](ride/structures/common-structures/data-entry.md)
    * [Invocation](ride/structures/common-structures/invocation.md)
    * [Order](ride/structures/common-structures/order.md)
    * [ScriptResult](ride/structures/common-structures/script-result.md)
    * [ScriptTransfer](ride/structures/common-structures/script-transfer.md)
    * [Transfer](ride/structures/common-structures/transfer.md)
    * [TransferSet](ride/structures/common-structures/transfer-set.md)
    * [WriteSet](ride/structures/common-structures/write-set.md)
  * [Структуры транзакций](ride/structures/transaction-structures.md)
    * [BurnTransaction](ride/structures/transaction-structures/burn-transaction.md)
    * [CreateAliasTransaction](/ride/structures/transaction-structures/create-alias-transaction.md)
* [Типы данных](/ride/data-types.md)
* Функции
  * [Вызываемая функция](ride/functions/callable-function.md)
  * [Функция-верификатор](ride/functions/verifier-function.md)

> Посмотреть репозиторий документации на [Github](https://github.com/acrylplatform/acryl-documentation)
