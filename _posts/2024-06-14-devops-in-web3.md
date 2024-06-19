---
title: DevOps In Web3
author: DevOpsLondon2021
date: 2024-06-14
category: posts
layout: post
---

This guide will explain step by step how we can setup a CI/CD pipeline in Web3 project. 
If you come from web2 background and don't have any experience in web3 you can follow the guide and get the overall understanding what are the similartities and differences when it comes to setting up a robust DevOps pipeline/setup in web3. 

To keep it simple I have broken down the guide into multi sub-topics to give the gist of everything from starting to end. 

Feedback welcome -> [devopslondon2021@gmail.com](mailto:devopslondon2021@gmail.com)


Getting started
---------------
We will start with some understanding of the smart contract and deploying a basic "Hello World" smart contract on Ethereum node. 


Smart Contract
--------------
#### What are smart contracts?
<img src="{{ '/assets/images/smartcontract.png' | prepend: site.baseurl }}" alt="smartcontract" style="width: 80%;">

Smart contracts are computer programs that run on a blockchain. They execute automatically when certain conditions are met, without the need for a central authority or server. This makes transactions secure, transparent, and irreversible.

Smart contracts enable parties to trust the process without knowing each other. They automate transactions and agreements, ensuring they are carried out as intended without intermediaries like lawyers or banks. This makes them trustworthy and efficient for handling digital transactions and agreements.   

#### Simple Analogy: The Vending Machine
Imagine a vending machine:

You insert money and select an item.
The machine automatically checks the amount and dispenses the item without any human intervention.
Similarly, a smart contract automatically executes when its conditions are met. No intermediaries are needed, and the process is transparent and secure.


#### Importance of Smart Contracts
<img src="{{ '/assets/images/smartcontract-benefits.png' | prepend: site.baseurl }}" alt="Smart-contract-benefits" style="width: 60%;">

- **Automation**: They automatically execute transactions when conditions are met.
- **Trust**: They allow transactions between unknown parties without intermediaries.
- **Immutability**: Once published, their code cannot be changed, ensuring consistency and reliability.

Web3 wallets
------------
<img src="{{ '/assets/images/wallet.png' | prepend: site.baseurl }}" alt="wallet" style="width: 50%;">

Web3 wallets are digital tools that enable interaction with decentralized applications (dApps) on various blockchain platforms. Unlike traditional wallets that store currency, Web3 wallets manage cryptographic keys that prove ownership and allow users to sign transactions securely. These wallets are essential for participating in the broader ecosystem of Web3, including using cryptocurrencies, managing digital identities, and interacting with decentralized finance (DeFi) applications.

#### Key Features
**Security**: They store private keys securely, often encrypted on the device or using advanced security measures like hardware isolation.   
**Interoperability**: Many are designed to work across multiple blockchain networks.   
**User Control**: Users have full control over their assets without the need for intermediaries.

Popular Web3 Wallets
--------------------
- <span style="color: #D4AF37;">**MetaMask**</span>   
A versatile browser extension and mobile wallet for Ethereum and ERC-20 tokens, enabling direct interaction with decentralized applications.   
https://metamask.io/

- <span style="color: #D4AF37;">**Trust Wallet**</span>   
A mobile wallet supporting a wide range of cryptocurrencies and features for interacting with dApps across multiple blockchains.   
https://trustwallet.com/

- <span style="color: #D4AF37;">**Ledger Nano X**</span>   
A secure hardware wallet that supports multiple cryptocurrencies, ensuring cold storage of private keys and integration with Web3 applications.   
https://www.ledger.com/

- <span style="color: #D4AF37;">**Trezor Model T**</span>   
A pioneer in hardware wallets, offering robust security for storing private keys and supporting numerous cryptocurrencies and digital assets.   
https://trezor.io/

- <span style="color: #D4AF37;">**Coinbase Wallet**</span>   
A user-friendly wallet by Coinbase that allows full control over private keys and supports a wide variety of digital assets and dApp interactions.   
https://www.coinbase.com/en-gb/wallet/

Popular Web3 IDEs
-----------------
- <span style="color: #D4AF37;">**Remix IDE**</span>   
A powerful, open-source web and desktop application that is primarily used for Ethereum smart contract development. It’s easy to use for beginners and provides a solid suite of tools for writing, testing, and deploying smart contracts.   
[https://remix.ethereum.org](https://remix.ethereum.org)

- <span style="color: #D4AF37;">**Truffle Suite**</span>   
Truffle is one of the most popular development frameworks for Ethereum. It includes a development environment, testing framework, and asset pipeline. It’s known for its robust testing framework and network management for deploying to any number of public and private networks.   
[https://www.trufflesuite.com/truffle](https://www.trufflesuite.com/truffle)

- <span style="color: #D4AF37;">**Hardhat**</span>   
Hardhat is a development environment to compile, deploy, test, and debug Ethereum software. It’s known for its Hardhat Network, a local Ethereum network designed for development, which allows for advanced debugging and detailed error messages.   
[https://hardhat.org](https://hardhat.org)

- <span style="color: #D4AF37;">**MetaMask Snaps (Flask)**</span>   
Although primarily known as a cryptocurrency wallet, MetaMask Snaps extends its functionalities to allow developers to create and manage their own plugins. It’s increasingly being used as a platform to test and run Web3 applications directly within the browser.   
[https://metamask.io/flask/](https://metamask.io/flask/)

- <span style="color: #D4AF37;">**Visual Studio Code with Blockchain Extensions**</span>   
VS Code isn’t a blockchain-specific IDE, but with extensions like Solidity and Ethereum Blockchain Workbench, it becomes a powerful tool for smart contract development and other blockchain-related coding.   
[https://code.visualstudio.com/](https://code.visualstudio.com/)

- <span style="color: #D4AF37;">**Etherlime**</span>   
An Ethereum development framework based on ethers.js. It provides fast deployment, compilation, and testing of Ethereum applications.   
[https://etherlime.readthedocs.io/](https://etherlime.readthedocs.io/)

DevOps in Web2 vs. Web3
-----------------------

| **Aspect**                    | **DevOps in Web2**                                                                                   | **DevOps in Web3**                                                                                                         |
|-------------------------------|-----------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| **Infrastructure**            | Centralized servers and data centers.                                                               | Decentralized, often distributed across nodes in a blockchain network.                                                    |
| **Deployment Targets**        | Traditional cloud environments (AWS, Azure, Google Cloud, etc.).                                    | Blockchain nodes, decentralized applications (dApps), and smart contract platforms.                                       |
| **Security Focus**            | Primarily on securing the server, database, and application layers from unauthorized access.        | Emphasizes the security of transactions, smart contracts, and ensuring the integrity of blockchain protocols.              |
| **Scaling**                   | Vertical and horizontal scaling through additional servers or instances.                            | Scaling through network consensus, layer 2 solutions, and sharding techniques.                                            |
| **Data Management**           | Centralized databases managed through SQL or NoSQL systems.                                         | Data is distributed across blockchain, requiring new approaches to querying and transaction handling.                     |
| **Development Practices**     | Emphasizes continuous integration and deployment using automated pipelines.                         | Involves continuous integration but requires additional considerations for immutable deployments and upgrade patterns.   |
| **Tooling**                   | Standard DevOps tools like Jenkins, Kubernetes, Docker, etc.                                        | Requires blockchain-specific tools such as Truffle, Hardhat, Ganache, and others for testing and deployment.              |
| **Monitoring and Logging**    | Focus on monitoring server performance, application logs, and user activity.                        | Monitoring node health, transaction performance, and smart contract interactions is crucial.                             |
| **Update and Rollback**       | Updates and rollbacks can be managed through standard deployment pipelines.                         | Smart contracts are often immutable, requiring careful planning and potential use of upgradeable proxy contracts.         |
| **Compliance and Regulations**| Compliance is generally focused on data privacy, security standards, and industry-specific regulations. | In addition to traditional compliance, there's a need to consider regulatory aspects specific to cryptocurrencies and tokenomics. |


Part 1 - Set up Development Environment
--------------------------------------

### Installing Node.js on a MacBook

### What is Node.js?
Node.js is a runtime environment that allows you to run JavaScript code outside of a web browser. It's essential for developing server-side applications and is widely used in blockchain application development.

### Why Node.js for Smart Contract Development?
Node.js is necessary to run JavaScript-based blockchain tools like **Truffle**, which is used to compile, deploy, and test Ethereum smart contracts. Node.js also manages dependencies and runs the development servers for your decentralized applications (DApps).

### Installation Steps:
#### Using Homebrew:
1. **Install Homebrew** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"  
2. **Intall Node.js using homebrew**:
Skip this step if you already have Node.js and npm on your system.  

```bash
brew install node
```
This command installs Node.js and npm (Node Package Manager), which is used to install JavaScript packages.

**Direct Download**:
- Visit the official Node.js website [Node.js](https://nodejs.org/en)
- Download the macOS installer recommended for most users.
- Follow the installation prompts to install Node.js and npm on your MacBook.

**Verify Installation**:
To confirm that Node.js and npm are correctly installed:

```bash
node -v
npm -v
```

Here is the reference of the version I used while documenting that worked well: 
```bash 
❯ node -v
v16.20.2
❯ npm -v
8.19.4
```

### Installing Truffle
Truffle is a development environment and framework for Ethereum that simplifies the processes of compiling, deploying, and testing blockchain applications.

**Installation**:
With Node.js and npm installed, install Truffle globally on your system:

```bash
npm install -g truffle
```
The -g flag installs Truffle globally, making it accessible from any terminal window.

**Verify Truffle Installation**:
```bash
truffle version
```
This command displays the version of Truffle installed, along with its dependencies.
Below are my system configuration at the time of documenting this tutorial. 
<img src="{{ '/assets/images/truffle-version.png' | prepend: site.baseurl }}" alt="truffleversion" style="width: 90%;">

Part 2 - Write a simple Smart Contract
-------------------------------------

### Setting Up a Project Directory:
```bash
mkdir hello-world-smartcontract
cd hello-world-smartcontract
truffle init
```
The truffle init command creates a new Truffle project with all necessary configuration files and directories for smart contract development.

This setup ensures you have a robust development environment on your MacBook for building, testing, and deploying smart contracts using Ethereum and Truffle.


- I will be using [VSCode](https://code.visualstudio.com/download) for the project development, feel free to use whatever IDE you prefer. Make sure you install `solidity` extension to beutify the syntax.

**Navigating to the contracts/ Folder**:
Truffle Project Structure: When you initialize a Truffle project using truffle init, it creates several directories. The contracts/ directory is where all your Solidity contracts are stored.

### Creating a New Contract:
Navigate to this directory by running `cd contracts/` in your terminal from the root of your Truffle project.

Create a new file called `HelloWorld.sol`. You can do this using a text editor or by running the command touch `HelloWorld.sol` in the terminal.

| Note: Solidity is a high-level programming language specifically designed for writing smart contracts on the Ethereum blockchain. We will cover a bit about Solidity in separate post. 


- Open the HelloWorld.sol file in a text editor.
- Start by specifying the Solidity compiler version at the top of the file. This ensures that the contract compiles with the correct version. Example:
```bash
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
```
- Define the smart contract with a name that corresponds to the filename:
```bash
contract HelloWorld {
    string public greeting = "Hello, World!";
    
    function setGreeting(string memory newGreeting) public {
        greeting = newGreeting;
    }
    
    function getGreeting() public view returns (string memory) {
        return greeting;
    }
}
```
Explanation:
- `string public greeting = "Hello, World!";` declares a state variable `greeting` that stores a string. `public` makes it automatically accessible outside the contract.
- `setGreeting` is a function that allows users to change the value of greeting.
- `getGreeting` is a function to retrieve the value of greeting.

Part 3 - Compile the Contract
----------------------------

### Purpose of Compilation

- **Convert Solidity to Bytecode**: The Solidity code you write is not directly understandable by the Ethereum Virtual Machine (EVM). truffle compile converts your human-readable Solidity code into EVM bytecode, which is deployable and executable on the Ethereum blockchain.
- **Generate ABI**: The compilation process also generates an Application Binary Interface (ABI). The ABI is a JSON format that defines how to interact with the contract including its functions and their parameters.

### How to Compile
- Return to the root of your Truffle project directory.
Run the command:
```bash
truffle compile
```
This command checks all Solidity files in the `contracts/` directory for any changes and compiles them into JSON artifacts located in the `build/contracts/` directory. These artifacts contain the `bytecode` and `ABI` for each compiled contract.

### Outcome of Compilation

- Upon successful compilation, Truffle will display a message in the terminal showing which contracts have been compiled and if there were any errors or warnings.
- The JSON artifacts in `build/contracts/` are what you will interact with in later steps when you migrate (deploy) the contracts to the blockchain and when you interact with them via client-side applications.

Here is what I saw when I compiled first time based on the above code: (Successful compilation)
```bash
❯ truffle compile

Compiling your contracts...
===========================
> Compiling ./contracts/HelloWorld.sol
> Artifacts written to /Users/devopslondon2021/Documents/Github/devops-ethereum-hello-world/build/contracts
> Compiled successfully using:
   - solc: 0.8.21+commit.d9974bed.Emscripten.clang
```

Part 4 - Test the Contract
-------------------------
We will be using `Ganache` - comes with truffle to test contracts locally.

### Why Use Ganache?
- **Simulation of Ethereum Environment**: Ganache simulates full Ethereum client behavior, making it an ideal tool for development and testing. It allows developers to see how their contracts would behave on an actual Ethereum network without the need for real ETH or live tokens.  
- **Speed and Safety**: Transactions on Ganache are instantaneous and free, providing a fast and risk-free environment to iron out any kinks in the application or smart contract.  

### Install and Set Up Ganache
- Download Ganache: Go to the [Truffle Ganache website](https://archive.trufflesuite.com/ganache/) and choose the appropriate version for your operating system (Windows, macOS, or Linux). I am going to pick MacOs one. 

### Validate Ganache Setup

- **Open Ganache**: Launch Ganache from your applications menu or desktop shortcut.
- **Check for Running Instance**: When Ganache opens, it should automatically create a new Ethereum blockchain workspace. You’ll see a screen displaying blockchain parameters such as accounts, each with a balance of simulated Ether, current block number, gas limit, and network ID.
- **Note Configuration**: Pay attention to the RPC server information (e.g., HTTP://127.0.0.1:7545). You’ll need these details for configuring Truffle.

<img src="{{ '/assets/images/ganache.png' | prepend: site.baseurl }}" alt="ganache" style="width: 90%;">

### Writing Tests
- Navigate to the `test/` directory in your Truffle project. This is where all test files should be placed.
- Create JavaScript test files here to write tests for your HelloWorld.sol contract. Truffle uses the Mocha testing framework and Chai for assertions by default, so you can use these to structure your tests.
- Example of a basic test file (`HelloWorldTest.js`):
```bash
const HelloWorld = artifacts.require("HelloWorld");

contract("HelloWorld", (accounts) => {
  it("should return the initial greeting 'Hello, World!'", async () => {
    const instance = await HelloWorld.deployed();
    const greeting = await instance.getGreeting();
    assert.equal(greeting, "Hello, World!", "The greeting was not initialized to 'Hello, World!'");
  });

  it("should change the greeting when setGreeting is called", async () => {
    const instance = await HelloWorld.deployed();
    await instance.setGreeting("Hello, Ethereum!");
    const updatedGreeting = await instance.getGreeting();
    assert.equal(updatedGreeting, "Hello, Ethereum!", "The greeting was not updated correctly");
  });
});
```

### Setup Test Environment
- Open your `truffle-config.js` and ensure the development network settings match Ganache’s RPC server settings (IP address and port).

Here is how my configuration looks - I have extended the default config file created by truffle init: 
```basg
module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 7545,  // This should match Ganache's RPC server port
      network_id: "*"
    },
  },
  compilers: {
    solc: {
      version: "0.8.0" 
    }
  },
  // Set default mocha options here, use special reporters, etc.
  mocha: {
    // timeout: 100000
  },
};
```

### Run Migrations
Before you can test your contracts, they need to be deployed to your local Ganache blockchain. This is done using Truffle migrations.

## Migrations Setup
- Verify that you have a migration script in the `migrations/` directory for deploying your `HelloWorld` contract. It might look something like this:
`1_deploy_contracts.js`
```bash
const HelloWorld = artifacts.require("HelloWorld");

module.exports = function(deployer) {
  // Deploy the HelloWorld contract without any arguments
  deployer.deploy(HelloWorld);
};
```


### Migration file name syntax

```bash 
<Number>_<Description>.js
```
- **Number**: A prefix number that determines the order in which the files are run. Numbers are typically sequential and start from 1.
- **Description**: A brief description of what the migration does, making it easier to understand the purpose of the file at a glance.

### Run Migration
To run your migrations, you would use the Truffle command:

```bash
truffle migrate

```

### Run Tests
- From the root of your Truffle project, execute:
```bash
truffle test
```
- This command compiles your contracts, deploys them to the Ganache blockchain, and runs the tests. Truffle will output the results of these tests, indicating whether each test passed or failed.

WARNING: You might run into issues if you are on latest Node.js version (v22.x.x) because that might not be compaitible with `µWS` (micro WebSockets). Make sure you use v16.x.x. Easiest way would be using `nvm` to downgrade the version. You have to reinstall truffle after downgrade and restart ganache. 
