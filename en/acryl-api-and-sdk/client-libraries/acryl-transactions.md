# acryl-transactions  [![npm version](https://badge.fury.io/js/%40acryl%2Facryl-transactions.svg)](https://badge.fury.io/js/%40acryl%2Facryl-transactions)

[![](https://img.shields.io/npm/l/make-coverage-badge.svg)](https://opensource.org/licenses/MIT) ![](https://img.shields.io/badge/Coverage-98.77%25-brightgreen.svg)

[_**Using this library**_](https://www.npmjs.com/package/@acryl/acryl-transactions) you can easily create and sign transactions for Acryl blockchain.  
It also allows you to multi-sign existing transactions or create them without signature at all.

This library is a set of transaction constructing functions:

* [Alias](https://acrylplatform.github.io/acryl-transactions/globals.html#alias)
* [Issue](https://acrylplatform.github.io/acryl-transactions/globals.html#issue)
* [Reissue](https://acrylplatform.github.io/acryl-transactions/globals.html#reissue)
* [Burn](https://acrylplatform.github.io/acryl-transactions/globals.html#burn)
* [Lease](https://acrylplatform.github.io/acryl-transactions/globals.html#lease)
* [Cancel lease](https://acrylplatform.github.io/acryl-transactions/globals.html#cancellease)
* [Transfer](https://acrylplatform.github.io/acryl-transactions/globals.html#transfer)
* [Mass transfer](https://acrylplatform.github.io/acryl-transactions/globals.html#masstransfer)
* [Set script](https://acrylplatform.github.io/acryl-transactions/globals.html#setscript)
* [Data](https://acrylplatform.github.io/acryl-transactions/globals.html#data)
* [Set asset script](https://acrylplatform.github.io/acryl-transactions/globals.html#setassetscript)
* [Order](https://acrylplatform.github.io/acryl-transactions/globals.html#order)

Check full documentation on [GitHub Pages](https://acrylplatform.github.io/acryl-transactions/index.html).

### Transactions

The idea is really simple - you create transaction and sign it from a minimal set of required params.  
If you want to create [Transfer transaction](https://acrylplatform.github.io/acryl-transactions/interfaces/itransfertransaction.html) the minimum you need to provide is **amount** and **recipient** as defined in [Transfer params](https://acrylplatform.github.io/acryl-transactions/interfaces/itransferparams.html):

```js
const { transfer } = require('@acryl/acryl-transactions')
const seed = 'some example seed phrase'
const signedTranserTx = transfer({ 
  amount: 1,
  recipient: '3P6fVra21KmTfWHBdib45iYV6aFduh4WwC2',
  //Timestamp is optional but it was overrided, in case timestamp is not provided it will fallback to Date.now(). You can set any oftional params yourself. go check full docs
  timestamp: 1536917842558 
}, seed)
```

Output will be a signed transfer transaction:

```js
{
  id: '8NrUwgKRCMFbUbqXKQAHkGnspmWHEjKUSi5opEC6Havq',
  type: 4,
  version: 2,
  recipient: '3P6fVra21KmTfWHBdib45iYV6aFduh4WwC2',
  attachment: undefined,
  feeAssetId: undefined,
  assetId: undefined,
  amount: 1,
  fee: 100000,
  senderPublicKey: '6nR7CXVV7Zmt9ew11BsNzSvVmuyM5PF6VPbWHW9BHgPq',
  timestamp: 1536917842558,
  proofs: [
    '25kyX6HGjS3rkPTJRj5NVH6LLuZe6SzCzFtoJ8GDkojY9U5oPfVrnwBgrCHXZicfsmLthPUjTrfT9TQL2ciYrPGE'
  ]
}
```

You can also create transaction, but not sign it:

```javascript
const unsignedTransferTx = transfer({ 
  amount: 1,
  recipient: '3P6fVra21KmTfWHBdib45iYV6aFduh4WwC2',
  //senderPublicKey is required if you omit seed
  senderPublicKey: '6nR7CXVV7Zmt9ew11BsNzSvVmuyM5PF6VPbWHW9BHgPq' 
})
```

Now you are able to POST it to Acryl API or store for future purpose or you can add another signature from other party:

```js
const otherPartySeed = 'other party seed phrase'
const transferSidnedWithTwoParties = transfer(signedTranserTx, seed)
```

So now there are two proofs:

```js
{
  id: '8NrUwgKRCMFbUbqXKQAHkGnspmWHEjKUSi5opEC6Havq',
  type: 4,
  version: 2,
  recipient: '3P6fVra21KmTfWHBdib45iYV6aFduh4WwC2',
  attachment: undefined,
  feeAssetId: undefined,
  assetId: undefined,
  amount: 1,
  fee: 100000,
  senderPublicKey: '6nR7CXVV7Zmt9ew11BsNzSvVmuyM5PF6VPbWHW9BHgPq',
  timestamp: 1536917842558,
  proofs: [
    '25kyX6HGjS3rkPTJRj5NVH6LLuZe6SzCzFtoJ8GDkojY9U5oPfVrnwBgrCHXZicfsmLthPUjTrfT9TQL2ciYrPGE',
    'CM9emPzpe6Ram7ZxcYax6s7Hkw6698wXCMPSckveFAS2Yh9vqJpy1X9nL7p4RKgU3UEa8c9RGXfUK6mFFq4dL9z'
  ]
}
```



