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


Part 1: Set up Development Environment
--------------------------------------

## Installing Node.js on a MacBook

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

**Setting Up a Project Directory**:
```bash
mkdir hello-world-smartcontract
cd hello-world-smartcontract
truffle init
```
The truffle init command creates a new Truffle project with all necessary configuration files and directories for smart contract development.

This setup ensures you have a robust development environment on your MacBook for building, testing, and deploying smart contracts using Ethereum and Truffle.

{% note %}
I will be using [VSCode](https://code.visualstudio.com/download) for the project development, feel free to use whatever IDE you prefer.
{% endnote %}
