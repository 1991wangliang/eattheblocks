# Arbitrage Uniswap Sushiswap Tutorials


## Prerequisites 
* npm 
> [install nodejs](https://nodejs.org/en/download/)
* sol  
> execue command: `sudo npm install -g solc@0.8.12`
* truffle 
> execue command: `sudo npm install -g truffle@5.5.3`

* truffle/hdwallet-provider 
> execue command: `sudo npm install @truffle/hdwallet-provider@1.7.0`


## Execute Steps 

* install node dependencies
> execute: `npm install`

* compile smart contract

> execute `truffle compile`

* setting network

setting smart contract network and infuraKey on truffle-config.js

```

/**
 * Use this file to configure your truffle project. It's seeded with some
 * common settings for different networks and features like migrations,
 * compilation and testing. Uncomment the ones you need or modify
 * them to suit your project as necessary.
 *
 * More information about configuration can be found at:
 *
 * trufflesuite.com/docs/advanced/configuration
 *
 * To deploy via Infura you'll need a wallet provider (like @truffle/hdwallet-provider)
 * to sign your transactions before they're sent to a remote public node. Infura accounts
 * are available for free at: infura.io/register.
 *
 * You'll also need a mnemonic - the twelve word phrase the wallet uses to generate
 * public/private key pairs. If you're publishing your code to GitHub make sure you load this
 * phrase from a file you've .gitignored so it doesn't accidentally become public.
 *
 */

const HDWalletProvider = require('@truffle/hdwallet-provider');
const infuraKey = "fj4jll3k.....";

//
// const fs = require('fs');
// const mnemonic = fs.readFileSync(".secret").toString().trim();

module.exports = {
  /**
   * Networks define how you connect to your ethereum client and let you set the
   * defaults web3 uses to send transactions. If you don't specify one truffle
   * will spin up a development blockchain for you on port 9545 when you
   * run `develop` or `test`. You can ask a truffle command to use a specific
   * network from the command line, e.g
   *
   * $ truffle test --network <network-name>
   */
  contracts_build_directory: './frontend/src/contracts',

  networks: {
    // Useful for testing. The `development` name is special - truffle uses it by default
    // if it's defined here and no other network is specified at the command line.
    // You should run a client (like ganache-cli, geth or parity) in a separate terminal
    // tab if you use this network and you must also set the `host`, `port` and `network_id`
    // options below to some value.
    //
    // development: {
    //  host: "127.0.0.1",     // Localhost (default: none)
    //  port: 8545,            // Standard Ethereum port (default: none)
    //  network_id: "*",       // Any network (default: none)
    // },
    // Another network with more advanced options...
    // advanced: {
    // port: 8777,             // Custom port
    // network_id: 1342,       // Custom network
    // gas: 8500000,           // Gas sent with each transaction (default: ~6700000)
    // gasPrice: 20000000000,  // 20 gwei (in wei) (default: 100 gwei)
    // from: <address>,        // Account to send txs from (default: accounts[0])
    // websockets: true        // Enable EventEmitter interface for web3 (default: false)
    // },
    // Useful for deploying to a public network.
    // NB: It's important to wrap the provider as a function.
    // Useful for private networks
    // private: {
    // provider: () => new HDWalletProvider(mnemonic, `https://network.io`),
    // network_id: 2111,   // This network is yours, in the cloud.
    // production: true    // Treats this network as if it was a public net. (default: false)
    // }

    // add bsc test provider info
    bscTestnet: {
      provider: () => new HDWalletProvider(
        infuraKey, 
        'https://data-seed-prebsc-1-s1.binance.org:8545'
      ),
      network_id: 97,
      skipDryRun: true
    },
  },

  // Set default mocha options here, use special reporters etc.
  mocha: {
    // timeout: 100000
  },

  // Configure your compilers
  compilers: {
    solc: {
      version: "0.8.0",    // Fetch exact version from solc-bin (default: truffle's version)
      // docker: true,        // Use "0.5.1" you've installed locally with docker (default: false)
      // settings: {          // See the solidity docs for advice about optimization and evmVersion
      //  optimizer: {
      //    enabled: false,
      //    runs: 200
      //  },
      //  evmVersion: "byzantium"
      // }
    }
  }
};


```

* deploy smart contract 

```
sudo truffle migrate --reset --network bscTestnet

```

## Output Logs
```

Compiling your contracts...
===========================
> Everything is up to date, there is nothing to compile.


Starting migrations...
======================
> Network name:    'bscTestnet'
> Network id:      97
> Block gas limit: 30000000 (0x1c9c380)


1_initial_migration.js
======================

   Deploying 'Migrations'
   ----------------------
   > transaction hash:    0x83c054ee9489575895805ab77ed37f74d0e6df18f978142776696ace80c954d8
   > Blocks: 2            Seconds: 4
   > contract address:    0x06aa991D94CA01837DD26Ee58992BB284b0077Ad
   > block number:        17498430
   > block timestamp:     1647096180
   > account:             0xe4b2c5217EE1F4e6f5FF51F11396318530FE5F77
   > balance:             1.41151094
   > gas used:            192159 (0x2ee9f)
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.00192159 ETH

   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.00192159 ETH


2_deploy_contracts.js
=====================

   Deploying 'Arbitrage'
   ---------------------
   > transaction hash:    0x1a162d9e91b5d09495980ea4d555448d739639a735307c472dc03ca9e6f24ca0
   > Blocks: 3            Seconds: 8
   > contract address:    0x9e7e653E57a17eB0612370240e1d3E02Fb57d6DB
   > block number:        17498436
   > block timestamp:     1647096198
   > account:             0xe4b2c5217EE1F4e6f5FF51F11396318530FE5F77
   > balance:             1.3978325
   > gas used:            1325506 (0x1439c2)
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01325506 ETH

   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.01325506 ETH

Summary
=======
> Total deployments:   2
> Final cost:          0.01517665 ETH

```

## Link

https://www.youtube.com/watch?v=AS_8_C5fTOE&list=PLvlChfJP2hjwehyaXUhyGFKaBEOf7Vyx_&index=1&t=1s