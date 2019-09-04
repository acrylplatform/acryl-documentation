# ScriptResult

Структура результата выполнения вызываемой функции.

## Конструктор

``` ride
ScriptResult(writeSet: WriteSet, transferSet: TransferSet)
```

## Поля

|   #   | Название | Тип данных | Описание |
| :--- | :--- | :--- | :--- |
| 1 | writeSet | WriteSet | Список записей [хранилища данных аккаунта](/blockchain/account-data-storage.md) |
| 2 | transferSet | TransferSet | Список переводов токенов |
