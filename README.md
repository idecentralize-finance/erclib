# erclib
[![Version npm](https://img.shields.io/npm/v/@idecentralize/erclib.svg?logo=npm)](https://www.npmjs.com/package/@idecentralize/erclib)
[![Node.js CI](https://github.com/idecentralize-finance/erclib/actions/workflows/npm-publish.yml/badge.svg)](https://github.com/idecentralize-finance/erclib/actions/workflows/npm-publish.yml)
[![Socket Badge](https://socket.dev/api/badge/npm/package/@idecentralize/erclib)](https://socket.dev/npm/package/@idecentralize/erclib)

ERC library for blockchain Development


In development. More networks, asset's and features are coming...

## Install and import

```npm install @idecentralize/erclib```

> *address should be checksumed*

## Usage

### Retrieve the chain id from your current provider or configuration
```javascript
// using ethersV6
import {BrowserProvider} from "ethers";
const provider = new BrowserProvider(window.ethereum);
const chainId = (await PROVIDER.getNetwork()).chainId.toString() 
```

### import your library
   - ERC20
   - ERC721 
   - NETWORK
   - ROUTER
   - IPFS_SVG_PATH

Example of the NETWORK object entry
```javascript
        id: 137,
        network: "Polygon",
        chain: "MATIC",
        chainId: 137,
        type: "Mainnet",
        rpc:"https://polygon-rpc.com",
        explorer: "https://polygonscan.com/address/",
        color: "#8247e5",
        defaultNFT: "0x5265535c7
```

Show the chain native currency logo
```javascript
import {IPFS_SVG_PATH, NETWORK} from "@idecentralize/erclib";
<Network src={`${IPFS_SVG_PATH}${NETWORK[chainId].chain}.svg`}/>
   
```

```javascript 
const rpc = NETWORK[chainId].rpc
const usdc = "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48";
const decimals = ERC20[chainId][usdc].decimals 
const CToken = ERC20[chainId][usdc].compound
const color = ERC20[chainId][usdc].colors
```

> FORKING :
> network_id should be the chain id return by the provider.
> When forking the mainnet using hardhat, the network id is 31337 and we want to use the mainnet asset under network id 1.


```javascript
ERC20[network_id === 31337 ? 1 : network_id][usdc].decimals  // output decimals of asset
```

# Supported Network
- IPFS
- Ethereum
- Polygon
- BSC
- Aurora
- Avanlance
- xDai

# Supported Testnet & protocols

- Compound 
- Aave 
- Yearn v2 

Please report any issues!

To add some assets, please submit a PR and provide the new IPFS CID.


