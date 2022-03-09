# Create Pool PancakeSwap Tutorials 

## Prerequisites 
* npm 
> [install nodejs](https://nodejs.org/en/download/)
* sol  
> execue command: `sudo npm install -g solc@0.8.12`
* truffle 
> execue command: `sudo npm install -g truffle@5.5.3`

## Execute Steup 
* Get MateMask Test PrivateKey (BSC-Testnet)

MetaMask Network Setting 
```
Network Name: Smart Chain - Testnet
New RPC URL: https://data-seed-prebsc-1-s1.binance.org:8545/
ChainID: 97
Symbol: BNB
Block Explorer URL: https://testnet.bscscan.com
```

* Get Binance Smart Chain Faucet 

https://testnet.binance.org/faucet-smart


* Build Project 

> npm install 

> truffle compile 

* Execute Deploy 

> truffle exec ./scripts/deploy-pool.js --network=bscTestnet

## Output logs
```
Using network 'bscTestnet'.

balance LP: 9000
```
## Link

https://www.youtube.com/watch?v=g7TuczcklrY&t=163s

