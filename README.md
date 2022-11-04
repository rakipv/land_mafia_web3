
## Documentation Contents

- [Installation & Set Up](#Installation-&-Set-Up)
  - [Downloading repository](#Downloading-repository)
  - [Setting up Blockchain on Local Network](#Setting-up-Blockchain-on-Local-Network)
  - [Setting up Blockchain on Ethereum Rinkeby Test Network](#Setting-up-Blockchain-on-Ethereum-Rinkeby-Test-Network)
  - [Setting up Client Application](#Setting-up-Client-Application)
- [Security & Testing](#Security--Testing)
  - [Smart Contracts Funtionality Testing](#Smart-Contracts-Funtionality-Testing)
  - [Smart Contracts Security Testing & Analysis](#Smart-Contracts-Security-Testing-Analysis)
- [Use-Cases](#Use-Cases)
  - [Registering Institutes by Central Authority](#Use-Case-1-Registering-Institutes)
  - [Issuing Certificates by Institutes](#Use-Case-2-Issuing-Certificates)
  - [Issuing Certificates by Institutes](#Use-Case-2-Issuing-Certificates)
  - [Viewing Certificates by Employers/Public](#Use-Case-4-Viewing-Certificates)

---

## Installation & Set Up


There are two ways to set up local blockchain with Truffle Ganache, either with GUI or CLI.

1. Create a `.env` file

Populate the following environment variables:

```
LOCAL_ENDPOINT=http://127.0.0.1:8545
NETWORK_ID=1337
```

> The port number and network ID can be changed to your preference


2. Download Truffle

Visit https://www.trufflesuite.com/truffle for more information


> Truffle helps us with deployment, testing, migration, etc.

3. Install node dependencies

npm install


#### Option 1 - Using Ganache GUI

1. Download Ganache GUI

Visit [Truffle Ganache](https://www.trufflesuite.com/ganache) to download the application

2. Create a ganache workspace & run ganache blockchain network

Click on 'New Workspace' and under 'Add Project', select the `truffle-config.js` file in the samoarkadirectory. This should create a new workspace project with the same truffle settings defined in the `truffle-config.js` file.



Once created with the workspace open, the local ganache blockchain network should be running on the defined port and network ID.

> Note: This blockchain network will be running as long as the Ganache GUI Application is open with the workspace.

3. Deploy Smart Contracts

Npm scripts has been included for ease of contract deployment. You may view the commands used under `package.json` for better understanding

In the root directory of Certoshi

```bash
truffle compile
npm run deploy:local
```

Option 2 - Using Ganache CLI

In your terminal/bash

1. Install Ganache CLI

```bash
npm install -g ganache-cli
```

2. Run Ganache blockchain network

```bash
npm run ganache
```

In the root directory of Certoshi

3. Deploy Smart Contracts

```bash
npm run deploy:local
```

 Setting up Blockchain on Ethereum Rinkeby Test Network


Getting ether on Rinkeby
 Visit the [Rinkeby faucet](https://faucet.rinkeby.io/) and follow the instructions on the page to get some ether transferred to your account.

Deploying Smart Contracts

We will be using Infura to help us deploy easily on our development set up with truffle.
(https://infura.io/) to create an ethereum project. 
Click on settings and change the 'endpoints' to Rinkeby and copy the endpoint link for the environment variables below.  
For the mnemonic, use your metamask account mneumonic.

```
PROJECT_ENDPOINT=https://rinkeby.infura.io/v3/12345
MNEMONIC="<your account's mnemonic with the ether on rinkeby>"
```

Connect to the rinkeby test network in your metamask and then, deploy the smart contracts.

```bash
npm run deploy:testnet
```

setting up Client Application

The client application (which is built with [React.js](https://reactjs.org/)) is located under the `/client` folder in the directory.

```bash
cd client
```

1. Install dependencies

```bash
npm install
```

2. Create a `.env`file

Populate the following environment variables:

```
REACT_APP_INFURA_PROJECT_ENDPOINT=https://rinkeby.infura.io/v3/12345
REACT_APP_LOCAL_ENDPOINT=http://127.0.0.1:8545
REACT_APP_NETWORK_ID=1337

```
 Start application

### Option 1 - To connect to local blockchain network

```bash
npm start
```

To use the front-end application running at http://localhost:3000/, connect to the Localhost Network in metamask


