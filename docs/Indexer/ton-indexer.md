# TON Blockchain Indexer

The **TON (The Open Network)** blockchain is a decentralized, high-performance blockchain platform designed to offer fast, scalable, and secure services for a wide range of applications. Originally developed by the team behind Telegram, TON aims to provide a solution for scalable digital payments, decentralized applications (dApps), and the broader blockchain ecosystem.

## Key Features

### 1. **High Scalability**
   - TON uses a **multi-chain architecture**, meaning it can split tasks across multiple chains to increase scalability. This allows the network to process millions of transactions per second (TPS).
   - The network features a **sharding** mechanism that divides the blockchain into multiple smaller chains, each responsible for a portion of the data and computation.

### 2. **Proof-of-Stake (PoS) Consensus**
   - TON employs a **Proof-of-Stake (PoS)** consensus mechanism, where validators stake tokens to participate in block validation and network security.
   - PoS helps reduce energy consumption compared to Proof of Work (PoW) and enables faster transaction finality.

### 3. **Instant Finality**
   - TON supports **instant transaction finality**, meaning transactions are confirmed and cannot be reversed within seconds after being processed, ensuring faster settlements.

### 4. **Decentralized Applications (dApps)**
   - TON is designed to support the development and deployment of decentralized applications (dApps) directly on the blockchain. It includes a **virtual machine** (TVM) that supports smart contract execution.

### 5. **TON Services**
   - TON provides a range of services, including:
     - **TON Payments**: A payment system integrated with the blockchain, enabling fast and cheap transfers.
     - **TON DNS**: A decentralized domain name system (DNS), allowing users to register human-readable addresses instead of using lengthy cryptographic addresses.
     - **TON Storage**: A decentralized file storage system that allows for secure and distributed data storage.
   
## TON Blockchain Components

### 1. **TON Tokens (TON)**
   - **TON** is the native cryptocurrency of the TON blockchain. It serves several purposes, including:
     - **Staking**: Used for staking to participate in the consensus mechanism and earn rewards.
     - **Transaction Fees**: Paid as fees to process transactions and smart contracts.
     - **Governance**: TON holders participate in the governance and decision-making of the network.

### 2. **Sharding**
   - One of the most innovative aspects of TON is its **multi-layer sharding architecture**, where multiple blockchains (shards) work in parallel to distribute the processing of transactions and data across the network.
   - Shards can operate independently while still being interconnected, allowing TON to scale seamlessly without sacrificing decentralization.

### 3. **TON Virtual Machine (TVM)**
   - The **TON Virtual Machine** is the execution environment for smart contracts on the TON blockchain.
   - TVM is optimized for performance and supports the execution of decentralized applications (dApps) written in a variety of programming languages.

### 4. **TON Blockchain Structure**
   - TON is structured as a multi-layered architecture consisting of:
     - **Masterchain**: The main chain that coordinates the overall network and is responsible for managing shard blocks and ensuring the integrity of the network.
     - **Workchains**: These are the sharded chains responsible for performing the majority of transaction processing.
     - **Shards**: Smaller segments of the network that handle transactions and smart contract execution within the workchains.

## Use Cases

### 1. **Decentralized Finance (DeFi)**
   - TON enables the creation of decentralized finance applications such as lending, borrowing, decentralized exchanges (DEX), and yield farming, leveraging its scalability and fast finality.

### 2. **Digital Payments**
   - With its fast transaction processing, TON is optimized for use as a **digital payment system**, enabling microtransactions and cross-border payments with low fees and quick settlement times.

### 3. **NFTs (Non-Fungible Tokens)**
   - TON allows the creation and trading of **NFTs** on the blockchain, providing a decentralized marketplace for digital collectibles and other unique assets.

### 4. **dApps and Smart Contracts**
   - TON provides a platform for developing and deploying decentralized applications (dApps). Its robust smart contract capabilities enable the creation of complex applications that run autonomously without intermediaries.

### 5. **Decentralized Storage**
   - TON's decentralized file storage system enables users to store and retrieve data 

## Ton Indexer Health Check

1. **Logs**
 *   Read files in logs should be around the indexer depth that is set in docker compose
2. **Postman Api**
 *   `Get Latest Block` should be sufficient

## Ton Indexer Postman Test

1. Use `Get Latest Block` api.
2. In `Get Range of Block` set **sBlock** and **lBlock** in a way that they're both less that data.latestBlock.seqno field in `Get Latest Block` response.
3. Get data.latestBlock.transactions.transactionHash in `Get Latest Block` response and put it in **transactionHash** field in `Get Transfer By Transaction Hash`.