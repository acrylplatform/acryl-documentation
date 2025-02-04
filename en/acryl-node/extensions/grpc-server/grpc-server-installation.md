# gRPC Server installation

The [gRPC Server](/acryl-node/extensions/grpc-server.md) extension can be installed on the [node](/blockchain/node.md) by two methods: using [deb package](https://en.wikipedia.org/wiki/Deb_%28file_format%29) or using ZIP file.

## Installation via deb package

1. Download deb package from the Releases page (Assets section) on [Github](https://github.com/acrylplatform/Acryl/releases). For the [main network](/blockchain/blockchain-network/main-network.md) it is grpc-server\_{version number}\_all.deb file, for [test network](/blockchain/blockchain-network/test-network.md) it is grpc-server-testnet\_{version number}\_all.deb.

2. Install the package using the command:

``` console
sudo dpkg -i grpc-server_{version number}_all.deb
```

3. Add the following string to the configuration file:

``` console
acryl.extensions += com.acrylplatform.api.grpc.GRPCServerExtension
```

For the main network, the configuration file is located at /etc/acryl/acryl.conf, for the test network at /etc/acryl-testnet/acryl.conf.

4. Restart the node.

If the node is running in the main network, run the command:

``` console
sudo systemctl restart acryl
```

If the node is running in the test network, run the command:

``` console
sudo systemctl restart acryl-testnet
```

## Installation via ZIP file

1. Download grpc-server-{version number}.zip file from Releases page (Assets section) [on Github](https://github.com/acrylplatform/Acryl/releases).
2. Unpack the archive to the directory containing node's JAR-file.
3. Create a new configuration file or open the existing one and add to it the following string:

``` console
acryl.extensions += com.acrylplatform.api.grpc.GRPCServerExtension
```

4. Run command:

``` console
java -cp 'acryl-all-1.0.0.jar:grpc-server-1.0.0/lib/*' com.acrylplatform.Application {configuration file name}.conf
```
