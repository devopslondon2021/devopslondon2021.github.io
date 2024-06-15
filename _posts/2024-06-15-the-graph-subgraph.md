---
title: Subgraph
author: DevOpsLondon2021
date: 2024-06-15
category: posts
layout: post
---

A subgraph is a component of The Graph, a decentralized protocol used to index and query data from blockchain networks. Subgraphs allow developers to efficiently and accurately retrieve blockchain data for their decentralized applications (dApps) by defining the specific data they need and how it should be structured. 

<img src="{{ '/assets/images/subgraph.png' | prepend: site.baseurl }}" alt="subgraph" style="width: 80%;">

Image source: [https://thegraph.com/](https://thegraph.com/)

Key terms
---------

- <span style="color: #D4AF37;">**Manifest:**</span>  A subgraph manifest (subgraph.yaml) is a configuration file where the developer defines the data sources (e.g., smart contracts), the schema, and the data mappings.
- <span style="color: #D4AF37;">**Data Sources**</span>: These specify the smart contracts and blockchains from which data will be indexed.
- <span style="color: #D4AF37;">**Schema**</span>: Defined in a GraphQL schema file (schema.graphql), this outlines the structure of the data to be indexed.
- <span style="color: #D4AF37;">**Mappings**</span>: These are written in AssemblyScript and specify how to transform and store blockchain data into the defined schema.

Benefits
--------

- <span style="color: #D4AF37;">**Efficiency**</span>: Subgraphs provide an efficient way to query blockchain data without the need to directly interact with the blockchain for every request.
- <span style="color: #D4AF37;">**Structured Data**</span>: By defining schemas and mappings, subgraphs ensure that data is well-structured and easy to work with.
- <span style="color: #D4AF37;">**Real-time Updates**</span>: Subgraphs can provide real-time data updates as they index new blocks and events from the blockchain.
- <span style="color: #D4AF37;">**Decentralization**</span>: Using The Graph’s decentralized network ensures that data indexing and querying are resilient and trustless.

Limitations
-----------

- <span style="color: #D4AF37;">**Indexing Latency**</span>: Subgraphs may experience delays in indexing new data from the blockchain, which can impact real-time data availability, especially during high transaction volumes.
- <span style="color: #D4AF37;">**Complexity of Setup**</span>: Setting up and configuring subgraphs can be complex, requiring a good understanding of The Graph’s architecture, GraphQL, and blockchain data structures.
- <span style="color: #D4AF37;">**Scalability**</span>: While The Graph scales well for many use cases, extremely high data volumes and complex queries can lead to performance bottlenecks.
- <span style="color: #D4AF37;">**Limited Support for Chains**</span>: The Graph initially focused on Ethereum and has gradually added support for other blockchains. However, support for some newer or less popular chains may still be limited.
- <span style="color: #D4AF37;">**Centralization Concerns**</span>: Although The Graph is working towards full decentralization, parts of its infrastructure (such as the hosted service) have been centralized, which could be a concern for some projects prioritizing complete decentralization.

Alternatives
------------

- <span style="color: #E6E6FA;">**Covalent**</span>
    - <span style="color: #D4AF37;">**Description**</span>: Covalent provides a unified API to access blockchain data across multiple blockchains.
    - <span style="color: #D4AF37;">**Strengths**</span>: Offers a no-code solution for querying blockchain data, supports multiple blockchains, and provides rich data insights without requiring complex subgraph setups.
    - <span style="color: #D4AF37;">**Use Cases**</span>: Ideal for developers seeking a straightforward way to query blockchain data without deep technical setups.
- <span style="color: #E6E6FA;">**Dune Analytics**</span>
    - <span style="color: #D4AF37;">**Description**</span>: A platform for querying and visualizing blockchain data using SQL.
    - <span style="color: #D4AF37;">**Strengths**</span>: User-friendly interface, powerful data visualization tools, and support for collaborative queries.
    - <span style="color: #D4AF37;">**Use Cases**</span>: Popular among data analysts and developers who need to create custom reports and visualizations of blockchain data.
- <span style="color: #E6E6FA;">**Alchemy**</span>
    - <span style="color: #D4AF37;">**Description**</span>: Alchemy provides a suite of developer tools, including enhanced APIs for querying blockchain data.
    - <span style="color: #D4AF37;">**Strengths**</span>: High reliability, performance-focused APIs, and additional services like monitoring and debugging tools.
    - <span style="color: #D4AF37;">**Use Cases**</span>: Developers seeking robust and high-performance infrastructure for building and scaling dApps.
- <span style="color: #E6E6FA;">**Infura**</span>
    - <span style="color: #D4AF37;">**Description**</span>: Infura offers a scalable API suite for connecting to Ethereum and IPFS networks.
    - <span style="color: #D4AF37;">**Strengths**</span>: Reliable infrastructure, easy integration, and extensive developer support.
    - <span style="color: #D4AF37;">**Use Cases**</span>: Projects needing stable and scalable access to Ethereum and IPFS without managing their own nodes.
- <span style="color: #E6E6FA;">**Bitquery**</span>
    - <span style="color: #D4AF37;">**Description**</span>: Bitquery provides a set of data products and APIs for accessing blockchain data.
    - <span style="color: #D4AF37;">**Strengths**</span>: Supports multiple blockchains, provides deep analytics and data processing capabilities.
    - <span style="color: #D4AF37;">**Use Cases**</span>: Developers and analysts needing detailed blockchain data and analytics across various networks.
