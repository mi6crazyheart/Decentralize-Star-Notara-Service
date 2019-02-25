## Decentralize Star Notara Service

### Getting Started
In this project, we've built a Star Notary Service by using ERC 721 standard for creating Non-Fungible tokens. Here a user can use the following features -

- Create/Own a Star
- Put a Star for sale 
- Buy a Star
- Give Star token name & symbol
- Exachange Stars
- Transfor Stars 

##### Token Name & Symbol
- Token Name: Star World Token
- Token Symbol: SWT

### Token Address on Rinkeby Network
    0x0c85E6042AFbD366b35FE52B2208332C1280Bc18
    
### Truffle & Openzepplin version used
    Truffle - v5.0.5
    Openzepplin - 2.1.2
    
### Built With 
[truffle](https://truffleframework.com/) - Development & testing framework.

[truffle boxes](https://truffleframework.com/boxes) - Provide easy to use boilerplates codes for faster development.

[openzeppelin](https://openzeppelin.org/) - Framework for building Smart Contracts using Solidity.

[Mocha](https://mochajs.org/) - Javascript testing framework.

[Chai](https://www.chaijs.com/) - Javascript assertion library.


### How to use in devloper mode
- Clone the repo from - https://github.com/mi6crazyheart/Decentralize-Star-Notara-Service
- Open the package-lock.json and verify that `truffle-hdwallet-provider` and `openzeppelin-solidity` dependencies are installed. If not you can always install it with the commands:
 
        npm install --save truffle-hdwallet-provider 
        npm install --save openzeppelin-solidity

- Verify you have the Truffle (v5.0.2) latest installed if not use the command 

        npm install -g truffle

- For starting the development console, run:

        truffle develop
        
- For compiling the contract, inside the development console, run:

        compile
        
- For migrating the contract to the locally running Ethereum network, inside the development console, run:

        migrate --reset 
        
- For running unit tests the contract, inside the development console, run:

        test 
        
- For running the Front End of the DAPP, open another terminal window and go inside the project directory, and run:

        cd app
        npm run dev


### Deploy your Contract to Rinkeby
- Go to infura.io & create your account. Once you sign up, you will be sent an email. Confirm your email address.
- Then click on “Create New Project”.
- Now, from the endpoint, copy the link for Rinkeby network.
- Update your `truffle-config.js` file as shown below sexample code

        const HDWalletProvider = require('truffle-hdwallet-provider');
        const infuraKey = "<Infura PROJECT ID>";
        // const fs = require('fs');
        const mnemonic = "<METAMASK SEED>";

        module.exports = {

          networks: {
            development: {
              host: "127.0.0.1",     // Localhost (default: none)
              port: 9545,            // Standard Ethereum port (default: none)
              network_id: "*",       // Any network (default: none)
             },
            // Useful for deploying to a public network.
            // NB: It's important to wrap the provider as a function.
            rinkeby: {
              provider: () => new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
                network_id: 4,       // rinkeby's id
                gas: 4500000,        // rinkeby has a lower block limit than mainnet
                gasPrice: 10000000000
            },
          },

          // Set default mocha options here, use special reporters etc.
          mocha: {
            // timeout: 100000
          },

          // Configure your compilers
          compilers: {
            solc: {
              // version: "0.5.1",    // Fetch exact version from solc-bin (default: truffle's version)
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
        }
- Get Tokens from Public Faucet. You can use - https://faucet.rinkeby.io/ to get some ethers.
- Deploy the contract to Rinkeby using command 

        truffle migrate --reset --network rinkeby
    
### Author
* **Suresh Kumar Majhi** - [GitHub](https://github.com/mi6crazyheart)    
