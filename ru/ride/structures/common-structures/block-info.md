# BlockInfo

Структура [блока](/blockchain/block.md).

## Конструктор

``` ride
BlockInfo(timestamp: Int, height: Int, baseTarget: Int, generationSignature: ByteVector, generator: Address, generatorPublicKey: ByteVector)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | timestamp | Int | Unix-время создания [блока](/blockchain/block.md) |
| 2 | height | Int | [Высота блока](/blockchain/block/block-height.md) |
| 3 | baseTarget | Int | Сложность создания блока |
| 4 | generationSignature | ByteVector | Подпись ключевого блока |
| 5 | generator | Address | [Адрес](/blockchain/address.md) аккаунта, который создал блок |
| 6 | generatorPublicKey | ByteVector | Публичный ключ аккаунта, который создал блок |
