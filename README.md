# solidity-openzeppelin-sdk

## Proxy contract creation and upgrade using zos sdk:

https://github.com/OpenZeppelin/openzeppelin-sdk/blob/master/packages/lib/README.md

> JavaScript library for the OpenZeppelin smart contract platform.

OpenZeppelin SDK is a platform to develop, deploy and operate smart contract
projects on Ethereum and every other EVM and eWASM-powered blockchain.

This is the repository for the OpenZeppelin SDK JavaScript library. It is mainly used
by the
[`openzeppelin-sdk` command-line interface](https://github.com/OpenZeppelin/openzeppelin-sdk/tree/master/packages/cli#openzeppelin-sdk-command-line-interface-openzeppelincli),
which is the recommended way to use the OpenZeppelin SDK; but this library can also be
used directly to operate projects when a programmatic interface is
preferred or more flexibility and lower-level access is required.

## Install

First, install [Node.js](http://nodejs.org/) and [npm](https://npmjs.com/).
Then, install the OpenZeppelin SDK JavaScript Library running:

## Usage

```
Suppose there is a contract called MyContract in the file
contracts/MyContract.sol, already compiled to build/contracts/MyContract.json,
and that there is a development blockchain network running locally in port 9545.
```

```
Open a Node.js console:
```

```sh
node
```

```sh
> const { ZWeb3, Contracts, SimpleProject } = require('@openzeppelin/upgrades')
> // Initialize a web3 provider.
> ZWeb3.initialize("http://localhost:9545")
> // Load the contract.
> const MyContract = Contracts.getFromLocal('MyContract')
> // Instantiate a project.
> myProject = new SimpleProject('MyProject', { from: await ZWeb3.defaultAccount() })
> // Create a proxy for the contract.
> myProject.createProxy(MyContract).then(proxy => myProxy = proxy)
> // Make a change on the contract, and compile it.
> const MyContractUpgraded = Contracts.getFromLocal('MyContract')
> myProject.upgradeProxy(proxy, MyContractUpgraded)
```
