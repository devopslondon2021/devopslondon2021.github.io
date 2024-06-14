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
Security: They store private keys securely, often encrypted on the device or using advanced security measures like hardware isolation.
Interoperability: Many are designed to work across multiple blockchain networks.
User Control: Users have full control over their assets without the need for intermediaries.

#### Popular Web3 Wallets
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


Deploying simple smart contract
-------------------------------

This is a step-by-step introductory tutorial that will teach you how to create and deploy a smart contract on Ethereum. 

If you are new to blockchain development and don’t know where to start, or if you just want to understand how to deploy and interact with smart contracts, this guide is for you.

+ 1
+ 2
+ 3
+ 4
