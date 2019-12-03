# solidity-openzeppelin-sdk

## Proxy contract creation and upgrade using zos sdk:

https://github.com/OpenZeppelin/openzeppelin-sdk/blob/master/packages/lib/README.md

- Usage

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
