---
custom_edit_url: null
---

# Stellar Blockchain Indexer

Stellar is an open-source blockchain network designed to facilitate fast, low-cost, and scalable cross-border transactions. It aims to connect financial institutions and streamline payments across different currencies and platforms.

## Key Features

### 1. **Decentralized Payment Network**
   - Stellar operates as a decentralized platform for transferring value across borders.
   - It supports multiple assets and currencies, allowing users to send any form of value between different parties.

### 2. **Consensus Mechanism**
   - Unlike traditional blockchains that use Proof of Work (PoW) or Proof of Stake (PoS), Stellar uses the **Stellar Consensus Protocol (SCP)**.
   - SCP is a federated Byzantine agreement (FBA) system, where groups of trusted nodes reach consensus on transactions.
   - This method allows for faster and more efficient transactions compared to traditional blockchains.

### 3. **Low Transaction Fees**
   - One of the major advantages of Stellar is its extremely low transaction fees, which makes it ideal for micropayments and cross-border transfers.

### 4. **Speed and Scalability**
   - Stellar can handle thousands of transactions per second, with transaction finality in 3-5 seconds. This makes it scalable and efficient for large-scale use.

### 5. **Multi-Currency Support**
   - Stellar supports multiple currencies and assets, allowing users to trade and transfer not just cryptocurrencies, but also fiat currencies (USD, EUR, etc.).
   - Through the use of **anchors**, organizations can issue assets on Stellar's network. An anchor is a trusted entity that connects a given currency to Stellar's network.

## Stellar Components

### 1. **Lumens (XLM)**
   - The native cryptocurrency of the Stellar network is called **Lumens** (XLM).
   - Lumens are used to pay for transaction fees and to facilitate multi-currency transactions. They also help prevent spam attacks by requiring a minimum balance of Lumens in each account.

### 2. **Stellar Ledger**
   - The Stellar Ledger is the system of records that tracks all transactions and accounts on the network.
   - It ensures that all transactions are validated, stored securely, and transparently.

### 3. **Anchors**
   - Anchors are entities that hold deposits and issue assets on the Stellar network, effectively serving as a bridge between the Stellar network and real-world assets.
   - Examples include banks, payment providers, and remittance services.

### 4. **Stellar Smart Contracts**
   - Stellar has limited smart contract capabilities compared to other blockchains like Ethereum.
   - It uses **Stellar's Anchor Contracts** and **SCP** to create trust between participants without the need for complicated scripts.

### 5. **Horizon**
   - Horizon is an API server that connects to the Stellar network and enables developers to interact with the network.
   - It allows applications to submit transactions, access ledger data, and more.

## Use Cases

### 1. **Cross-Border Payments**
   - Stellar facilitates low-cost and fast cross-border payments, enabling financial institutions to connect and transfer funds across countries.
   - The use of anchors for asset conversion helps minimize exchange rate issues in cross-border transactions.

### 2. **Remittance**
   - Stellar is ideal for remittance services due to its low transaction fees and ability to transfer small amounts of money quickly.
   - It provides an alternative to traditional remittance services, reducing the cost and time involved.

### 3. **Decentralized Finance (DeFi)**
   - Stellar is increasingly being used to build decentralized financial services, such as lending, borrowing, and decentralized exchanges.

### 4. **Tokenization of Assets**
   - Stellar enables the creation of digital representations of real-world assets, such as real estate, commodities, or shares. These tokenized assets can be easily transferred and traded on the blockchain.

## Advantages of Stellar

- **Fast Transactions:** Transactions settle in 3-5 seconds.
- **Low Fees:** Transaction fees are extremely low, enabling micropayments.
- **Scalable:** Stellar can handle a high throughput of transactions per second.
- **Cross-Currency Transactions:** Supports multiple currencies and assets for seamless cross-border transactions.

## Stellar Indexer Health Check

1. **Logs**
 *   Read files in logs should be around the indexer depth that is set in docker compose
2. **Postman Api**
 *   `Get Latest Ledger` should be sufficient

## Stellar Indexer Postman Test

1. Use `Get Latest Ledger` api.
2. In `Get Range of Ledger` set **sLedger** and **lLedger** in a way that they're both less that data.latestBlock.ledgerSequence field in `Get Latest Ledger` response.
3. Get data.latestBlock.transactions.transactionHash in `Get Latest Ledger` response and put it in **transactionHash**  field in `Get Transfer By Transaction Hash`.
4. Get data.latestBlock.transactions.sourceAddress or data.latestBlock.transactions.operations.sourceAddress in `Get Latest Ledger` response and put it in **fromAddress** field in `Get Transfer By From Address`.