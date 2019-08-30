# PyAcryl
PyAcryl is an object-oriented Python interface to the Acryl blockchain platform. The library is developing by community and open source. Latest documentation and examples can be found in [Github repository](https://github.com/PyAcryl/PyAcryl/). 

## Getting Started

You can install PyAcryl using:

    pip install pyacryl

## Documentation

The library utilizes classes to represent various Acryl data structures:

- pyacryl.Address
- pyacryl.Asset
- pyacryl.AssetPair
- pyacryl.Order

#### Code Example
```python
import pyacryl as pw

myAddress = pw.Address(privateKey='CtMQWJZqfc7PRzSWiMKaGmWFm4q2VN5fMcYyKDBPDx6S')
otherAddress = pw.Address('3PNTcNiUzppQXDL9RZrK3BcftbujiFqrAfM')
myAddress.sendAcryl(otherAddress, 10000000)
myToken = myAddress.issueAsset('Token1', 'My Token', 1000, 0)
while not myToken.status():
	pass
myAddress.sendAsset(otherAddress, myToken, 50)

```



### Source code
[PyAcryl Github repository](https://github.com/PyAcryl/PyAcryl/)