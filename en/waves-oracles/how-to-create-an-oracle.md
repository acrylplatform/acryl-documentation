# How to create an oracle

The Waves Platform provides a catalogue for the search and creation of oracle cards — [https://oracles.wavesexplorer.com](https://oracles.wavesexplorer.com). Using the [Waves Oracles](/waves-oracles/about-waves-oracles.md) service, you can see which oracles have already been created by other developers and what data they write on the blockchain, or if you already have an oracle, you can publish your oracle card so that other users know it exists and can use it.

But the creation of the oracle as microservice which takes data from an outside world source and writes it on the blockchain, remains outside the scope of the Waves Oracles service.

This article based on a simple sample will shortly introduce you to full-cycle how and why to use Waves Oracles, how to implementation of the programme part of the oracle and launch your solution, and then use the oracle data in the [dApp](/blockchain/dapp.md).

## Example of an oracle

As a small example, the following use case should be considered now: imagine you have dApp and you want in it to access data of exchange rates: [WAVES](/blockchain/token/waves.md) per USD and WAVES per BTC, e.g.

If off-chain data is required for dApp to be executed, this data must be obtained and write on the [blockchain](/blockchain/blockchain.md), because dApp have access only to data stored on the blockchain. To retrieve data from the off-chain to blockchain, implementing small programs called oracles.

Our dApp requires quotation data on the blockchain. Therefore, we will create a new oracle, which will receive the relevant quotation data from the public Waves Data Service API once an hour and write it on the blockchain, and also create an oracle card so that other users in theirs decentralized applications can use this data if they have the same need.

## Implementation of the programme part of the oracle

First of all, let's create the main part of the oracle — programme that access to exchange rates data and write it to our account. Here we use TypeScript with Node.js, but you can use Python or any other programming language. List of [client libraries](/waves-api-and-sdk/client-libraries.md).

### Cron

Create a cron that will run our service to retrieve data from the API every hour:

``` typescript
import * as cron from 'node-cron';
import { WavesPrice } from './WavesPrice';
​
// run WavesPrice class every 1 hour
cron.schedule('0 0 */1 * * *', () => {
  new WavesPrice(logger);
});
```

### Get data and transaction sending

Create a service that will request data from the public Waves Data Services API.

Get the _lastPrice_ parameter from the API, shift the point by the required digits and assign a value to the corresponding keys:

``` typescript
lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/Ft8X1v1LTa1ABafufpaCWyVj8KkaxUWE6xBhW6sNFJck');
dataParams.push({ key: 'waves_usd_2', value: lastPrice * Math.pow(10, 2) });

lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS');
dataParams.push({ key: 'waves_btc_8', value: lastPrice * Math.pow(10, 8) });
```

The easiest and correct way is to create a new account for new oracle. Read about [account creation](/waves-client/account-management/creating-an-account.md).

Sign the [data transaction](/blockchain/transaction-type/data-transaction.md) by your oracle account SEED:

``` typescript
const signerDataTX = DataTX(params,'YOU ORACLE SEED HERE');
```

Send the signed data transaction on the blockchain. [Test network — pool.testnet.wavesnodes.com](https://pool.testnet.wavesnodes.com/api-docs/index.html), [main network — https://nodes.wavesnodes.com](https://nodes.wavesnodes.com/api-docs/index.html).

``` typescript
const result = await broadcast(signerDataTX, 'https://nodes.wavesnodes.com');
```

Creating an oracle card and other transactions requires a fee, so don't forget to top up your account balance. The first time you can try to create an oracle in the test network.

The code ends up looking like this:

``` typescript
import axios from 'axios';
import { data as DataTX, broadcast } from '@waves/waves-transactions';
​
​
export class WavesPrice {
​
  constructor() {
    this.start();
  }
​
  private async getLastprice(url: string): Promise<number> {
    const data = (await axios.get(url)).data.data;
    return data.lastPrice;
  }
​
  private async broadcastTX(dataParams) {
    const params = {
      data: dataParams
    };
​
    const signerDataTX = DataTX(params,'YOU ORACLE SEED HERE');
    const result = await broadcast(signerDataTX, 'https://nodes.wavesnodes.com');
  }
​
  public async start() {
    try {
      let dataParams = [];
      let lastPrice = 0;
​
      lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/Ft8X1v1LTa1ABafufpaCWyVj8KkaxUWE6xBhW6sNFJck');
      dataParams.push({ key: 'waves_usd_2', value: lastPrice * Math.pow(10, 2) });
​
      lastPrice = await this.getLastprice('https://api.wavesplatform.com/v0/pairs/WAVES/8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS');
      dataParams.push({ key: 'waves_btc_8', value: lastPrice * Math.pow(10, 8) });
​
      await this.broadcastTX(dataParams);
    } catch(err) {
      console.log(err);
    }
  }
}
```

### Project dependencies

This part sets the project dependencies:

``` typescript
{
  "name": "balance-oracle",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "axios": "0.19.0",
    "node-cron": "2.0.3",
    "@waves/waves-transactions": "3.16.3"
  },
  "scripts": {
    "start": "tsc ./project/src/app.ts && node ./project/src/app.js"
  },
  "devDependencies": {
    "@types/node": "^11.11.3"
  }
}
```

## Launching oracle

First, install Node.js, if it is not yet installed: [https://nodejs.org/en](https://nodejs.org/en).

Setting project dependencies:

``` bash
$ npm install
```

If you have not installed TypeScript, you need to install it globally:

``` bash
$ npm install -g ts-node typescript
```

Now let's launch our oracle:

``` bash
$ npm run start
```

In Waves Explorer we can see data transaction with exchange rates in the format that we wanted (fig. 1):

<img src="img/5_transaction_in_explorer.png" width="700"/>

Figure 1.

Creation of the oracle card
For other users to know about our oracle, we use Waves Oracles to create an oracle card.

Waves Oracles is a service that utilizes Waves Keeper.

To create an oracle card, use the same account you used to sign transactions in the code.

Open Waves Oracles, log in with Waves Keeper and hit the Create an oracle on sidebar menu (fig.2).



Figure 2.



On popup will be shown needs to fill certain information about the oracle.

Let's call our oracle "WAVES/USD and WAVES/BTC", select the category "Market data & exchange rates" — so users can find that oracle quickly. Сhoose the "Production" status, because the oracle is already working and available. Write a short oracle description in the About field. And the oracle updates the quotes data every hour, we specify it in the Update frequency field.

The up part of the form is shown in fig. 3.



Figure 3.



Coming down below and fill in the Specification and Example.

In our case, the oracle must write two quotation values: WAVES/USD and WAVES/BTC. Therefore, we define these two parameters, as shown in fig. 4.

Here we need some explanations: dApp on RIDE cannot use float value, that's why we use an integer type with point shift by the necessary number of digits. Also in the key, we specify the number of digits by which the point shifts: for USD by two digits, for BTC by eight digits. It'll be easy to parse keys like this by RIDE and realize how many characters the point is shifted.

The key like this is not unique and the account data storage will always retain the last value. You can add a timestamp to make the key unique and save historical values.



Figure 4.



After the form is filled, Approve the data transaction for the creation of the oracle card with Waves Keeper. Once we did so, the new oracle card is successfully registered in Waves Oracles. We can see oracle card protocol in Waves Explorer, as shown in fig. 5. After a while, the card will appear in the Waves Oracles interface.



Figure 5.

Usage of the oracle data
Congratulations, now our oracle is completely ready. Once data is written in the blockchain, every RIDE based dApp's can access this data (via the getInteger(), getString(), getBinary() and getBoolean() methods) and use it for their calculations, e.g., decide on the amount of payouts, sending of transactions, winners of a contest, etc.

In our case, for example, to get WAVES/BTC data from the oracle, you need to specify the oracle address and the corresponding key in getInteger() method:

getInteger("3PPTrTo3AzR56N7ArzbU3Bpq9zYMgcf39Mk", "waves_btc_8")
