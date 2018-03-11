# An Introduction to Blockchain Distributed Application (dApp) Development

![](images/decentralisedConsensus.png)

_Source: [Bitnation](https://tinyurl.com/nktt7tx)_

<div class="notes">
  Hit 'esc here to give a presentation overview.
</div>

- - -

## Overview

> + Your Peers
> + Introduction to [Provenator](https://github.com/glowkeeper/Provenator)
> + The dApp Development Ecosystem
> + The Constituent Parts of a dApp
> + Deploying the dApp
> + Wrapping Up

<div class="notes">
  Use 'cmd-' on a MAC to make the presentation slightly smaller. That will allow images to display properly. Use the spacebar to navigate, since that will move to the next slide correctly, even if the slides are vertically aligned.
</div>

# Your Peers

![](images/handshake.jpg)

_Source: [Forbes](https://tinyurl.com/y77aju68)_

- - -

## Me - Steven Huckle

+ 25+ years in IT
+ Trainee Cobol Programmer
+ BSc Computer Science
+ Unix Sys' Admin'
    - Reuters
    - Credit Suisse

## Me (cont'd)

+ MSc Music Technology
+ Audio programmer in Games
    - Sony
    - Zoe Mode (here in Brighton)
+ MSc Energy and the Environment
    - Bitcoin Mining
    - PhD in Blockchain Technologies

## University of Sussex

![](images/UoS_logo_black-01.jpg)

## Altalix

![](images/sunset-london.jpeg)

_Source: [Altalix](http://www.altalix.com/index.html)_

## You

![](images/Star-Wars-Girls-800px.png)

_Source: [Open Clipart](https://tinyurl.com/y7l7qvk7)_

# Introduction to Provenator

![](images/label.png)

_Source: [Open Clipart](https://tinyurl.com/yctu3ssl)_

- - -

## Fake news

[Provenator](https://github.com/glowkeeper/Provenator) is the result of an academic paper that was published recently in a Special Issue of a Mary-Ann Liebert journal, Big Data: [Fake News - a Technological Approach to Proving Provenance Using Blockchains](https://doi.org/10.1089/big.2017.0071).

## The Live dApp

[Provenator](https://gateway.ipfs.io/ipfs/QmesSUrVz4d6LyVgKx58wWTUbMq2FmnWJ96LNNKhwj95n6/#/)

# The dApp Development Ecosystem

![](images/ecosystemDevelopment.jpg)

_Source: [Berkeley Lab](https://www.energystorage.lbl.gov/battery-ecosystem/)_

- - -

## Dependant Packages

+ [node](https://nodejs.org/en/)
+ [npm](https://www.npmjs.com/)
+ [Ganache](https://github.com/trufflesuite/ganache)
+ [Truffle](https://github.com/trufflesuite/truffle)
+ [http-server](https://www.npmjs.com/package/http-server)

## An Editor

+ [Atom](https://atom.io/)
+ [browser Solidity](https://remix.ethereum.org)

## Revision Control

You are using [GitHub](https://github.com/), aren't you?

+ [SourceTree](https://www.sourcetreeapp.com/)

## GitHub Community of Practice

1. Fork [Provenator](https://github.com/glowkeeper/Provenator)
2. Clone fork to local machine
3. Check out master branch
4. Create topic branch
5. Write patches
6. Stage and Commit patches
7. Push the new branch back up to the GitHub fork
8. Send a Pull Request

## Get/Give Help

+ [StackExchange](https://stackexchange.com/)
+ [Gitter](https://gitter.im/ethereum/home)
+ Forums etc.

# The Constituent Parts of a dApp

![](images/fullStack.png)

_Source: [comic.browserling.com](https://comic.browserling.com/15)_

- - -

## dApp Overview

+ Blockchain backend smart contracts, built using [Solidity](https://solidity.readthedocs.io/)
+ A Javascript frontend, built using [React](https://reactjs.org/)
+ The glue that fits the both together - the Ethereum JavaScript API, [web3.js](https://github.com/ethereum/web3.js/).

## The Backend Blockchain

+ Smart contracts, built using [Solidity](https://solidity.readthedocs.io/)

## The Web Interface

+ A Javascript frontend, built using [React](https://reactjs.org/)
+ The Ethereum JavaScript API, [web3.js](https://github.com/ethereum/web3.js/).
+ The contract address.
+ The contract ABI.

## Sending/Receiving Transactions

**Asynchronous transactions**. When you call a smart contract's method, you create a blockchain transaction, and the return value will be a transaction hash, not the result from the method. That's because the method's result is only returned after the transaction has been mined. Hence, you need to _poll_ for the result, using an **async/await** pattern.

## Running the dApp

When running the dApp, [MetaMask](https://metamask.io/) stitches together the javascript frontend and the blockchain backend. It also manages your wallet, and signs the transactions created: [Using MetaMask](https://youtu.be/6Gf_kRE4MJU).

# Deploying the dApp

![](images/deployButton.jpg)

_Source: [abidibo.net](https://tinyurl.com/ydezua5t)_

- - -

## Deploying Locally

Run and test the dApp locally, before deploying to a public blockchain.

## Prerequisites

Download and install the dependencies (if you have not already done so):

+ [node](https://nodejs.org/en/)
+ [npm](https://www.npmjs.com/)
+ [Ganache](https://github.com/trufflesuite/ganache)
+ [Truffle](https://github.com/trufflesuite/truffle)
+ [http-server](https://www.npmjs.com/package/http-server)
+ [Provenator](https://github.com/glowkeeper/Provenator)

## Install

Run a local Ethereum blockchain via [Ganache](https://github.com/trufflesuite/ganache):

1. Change to the [Ganache](https://github.com/trufflesuite/ganache) repository's home directory
2. Run `npm install`
3. Run `npm start`
4. Ensure [Ganache](https://github.com/trufflesuite/ganache) is running on [http://localhost:8545](http://localhost:8545) (you may need to change its settings)

## Install (cont'd)

Install the **Provinator** repository's dependencies:

1. Change to the **Provinator** repository's home directory
2. Run `npm install`.

<div class="notes">
  `npm install` should install everything listed in the **Provinator** repository's _package.json_.
</div>

## Contract Deployment

Use [Truffle](https://github.com/trufflesuite/truffle) to publish the contracts to [Ganache](https://github.com/trufflesuite/ganache), your local blockchain instance:

1. Change to the **Provinator** smart contracts directory _blockchain/contracts_
2. Run `truffle migrate`.

## Point the Frontend at the Smart contracts

+ Edit the **Provinator** source file _app/utils/contractHandler.jsx_ so that the four static variables `premisObjectContractAddress`, `premisEventContractAddress`, `premisAgentContractAddress` and `premisRightsContractAddress` contain the addresses generated by `truffle migrate`, above. e.g

````
static premisObjectContractAddress = '0xb9bfd8ff77db391a28a45b6c1cb72b0028695219'
static premisEventContractAddress = '0x12dba0b95a32239a5ba3e6bf7d05471d18f30d1f'
static premisAgentContractAddress = '0xc3a182dd01e3d9ffdbe95ce568b9c8d936e2ca9d'
static premisRightsContractAddress = '0xec6a5f11e7865aadc61f27faf8707795c1cda868'
````

## Build the Frontend

Now create the web application:

1. In the **Provinator** repository's home directory, build the [React](https://reactjs.org/) frontend by typing `npm run watch`
2. Copy some needed resources to the build directory by typing `npm run copy`

## Load the dApp

1. Startup an instance of [http-server](https://www.npmjs.com/package/http-server) by typing `npm run start`
2. Fire up a [MetaMask](https://metamask.io/) enabled browser
3. Point MetaMask at your local running instance of the blockchain ([http://localhost:8545](http://localhost:8545)).
4. Import a wallet from Ganache.
5. In the browser, go to the URL [http://localhost:8081](http://localhost:8081)
6. Create a digital media resource and subsequently, get details about that resource.

## Deploying Publicly

+ The test Ethereum network, [Rinkeby](https://www.rinkeby.io)
+ [IPFS](https://ipfs.io/)

## Rinkeby

Use the _geth_ client to instantiate the test Ethereum network, [Rinkeby ](https://www.rinkeby.io):

1. _geth --testnet_

## Deploy to Rinkeby

Use [Truffle](https://github.com/trufflesuite/truffle) to publish the contracts to [Rinkeby](https://www.rinkeby.io):

1. Change to the **Provinator** smart contracts directory _blockchain/contracts_
2. Run `truffle migrate`.

## Point the Frontend at the Smart contracts

+ Edit the **Provinator** source file _app/utils/contractHandler.jsx_ so that the four static variables `premisObjectContractAddress`, `premisEventContractAddress`, `premisAgentContractAddress` and `premisRightsContractAddress` contain the addresses generated by `truffle migrate`, above. e.g

````
static premisObjectContractAddress = '0xb9bfd8ff77db391a28a45b6c1cb72b0028695219'
static premisEventContractAddress = '0x12dba0b95a32239a5ba3e6bf7d05471d18f30d1f'
static premisAgentContractAddress = '0xc3a182dd01e3d9ffdbe95ce568b9c8d936e2ca9d'
static premisRightsContractAddress = '0xec6a5f11e7865aadc61f27faf8707795c1cda868'
````

## Build the Frontend

Now create the web application:

1. In the **Provinator** repository's home directory, build the [React](https://reactjs.org/) frontend by typing `npm run watch`
2. Copy some needed resources to the build directory by typing `npm run copy`

## Deploy the Frontend to IPFS

[IPFS](https://ipfs.io/)

## Load the dApp

1. Fire up a [MetaMask](https://metamask.io/) enabled browser
2. Point MetaMask at [Rinkeby](https://www.rinkeby.io)
3. Use the [rinkeby faucet](https://www.rinkeby.io/#faucet) to fund your wallet
4. In the browser, go to the dApp URL [the address here](http://an.ipfs.address)
5. Create a digital media resource and subsequently, get details about that resource

# Wrapping Up

![](images/parcel.png)

_Source: [Open Clipart](https://openclipart.org/detail/220024/parcel-bw)_

- - -

## Session overview

> + Introduced [Provenator](https://github.com/glowkeeper/Provenator)
> + The dApp Development Ecosystem
> + The Constituent Parts of a dApp
> + Deploying the dApp

## Get Involved!

[Provenator](https://github.com/glowkeeper/Provenator) is an open source, free software project on GitHub...

# Thank You

![](images/adrian.png)

_Source: [BBC Sport](http://www.bbc.co.uk/sport/football/30808244)_

- - -
