# AcrylCS
A C# library for interacting with the Acryl blockchain

Supports node interaction, offline transaction signing, Matcher orders, and creating addresses and keys.

## Getting Started

You can download **AcrylCS.dll** from [releases](https://github.com/acrylplatform/AcrylCS/releases) and add it to your project's References and in your code as:
```
using AcrylCS;
```

If you want to work with full AcrylCS project as contributor you should use also all crypto **.dll** from releases in your References.

Target framework .NET Framework 4.5.1
## Documentation

The library utilizes classes to represent various Acryl data structures and encoding and serialization methods:

- AcrylCS.Node
- AcrylCS.Order
- AcrylCS.OrderBook
- AcrylCS.PrivateKeyAccount
- AcrylCS.Transaction
- AcrylCS.AddressEncoding
- AcrylCS.Base58
- AcrylCS.Utils


#### Code Example
Code examples are in [AcrylCSTests](https://github.com/acrylplatform/AcrylCS/tree/master/AcrylCSTests) project.

### Source code
[AcrylCS Github repository](https://github.com/acrylplatform/AcrylCS)
