# Установка gRPC Server

Расширение [gRPC Server](/acryl-node/extensions/grpc-server.md) можно установить на [узел](/blockchain/node.md) двумя способами: с помощью [deb-пакета](https://ru.wikipedia.org/wiki/Deb_%28формат_файлов%29) и с помощью ZIP-файла.

## Установка с помощью deb-пакета

1.&nbsp;Скачайте deb-пакет со страницы Releases (секция Assets) на [Github](https://github.com/acrylplatform/Acryl/releases). Для [основной сети](/blockchain/blockchain-network/main-network.md) это файл grpc-server\_{номер версии}\_all.deb, для [тестовой](/blockchain/blockchain-network/test-network.md) — grpc-server-testnet\_{номер версии}\_all.deb.

2.&nbsp;Установите пакет с помощью команды:

``` console
sudo dpkg -i grpc-server_{номер версии}_all.deb
```

3.&nbsp;В файл конфигурации добавьте следующую строчку:

``` console
acryl.extensions += com.acrylplatform.api.grpc.GRPCServerExtension
```

Для основной сети файл конфигурации находится по адресу /etc/acryl/acryl.conf, для тестовой — /etc/acryl-testnet/acryl.conf.

4.&nbsp;Перезапустите узел.

Если узел запущен в основной сети, выполните команду:

``` console
sudo systemctl restart acryl
```

Если узел запущен в тестовой сети, выполните команду:

``` console
sudo systemctl restart acryl-testnet
```

## Установка с помощью ZIP-файла

1.&nbsp;Скачайте ZIP-файл grpc-server-{номер версии}.zip со страницы Releases (секция Assets) [на Github](https://github.com/acrylplatform/Acryl/releases).

2.&nbsp;Распакуйте архив в директорию с JAR-файлом узла.

3.&nbsp;Создайте новый файл конфигурации или откройте существующий и добавьте в него строчку:

``` console
acryl.extensions += com.acrylplatform.api.grpc.GRPCServerExtension
```

4.&nbsp;Выполните команду:

``` console
java -cp 'acryl-all-1.0.0.jar:grpc-server-1.0.0/lib/*' com.acrylplatform.Application {название файла конфигурации}.conf
```
