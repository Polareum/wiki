---
custom_edit_url: null
---

# Solana Blockchain Indexer

**Solana** is a high-performance, decentralized blockchain platform designed to support scalable and efficient decentralized applications (**DApps**) and crypto-assets. It is known for its high throughput, low transaction costs, and innovative architecture.

### Key Features of Solana

1.  **High Scalability**:
    *   Solana achieves scalability through its unique consensus mechanism and architecture, allowing it to handle thousands of transactions per second (TPS).
2.  **Low Transaction Costs**:
    *   Transactions on Solana cost only a fraction of a cent, making it an attractive option for developers and users.
3.  **Proof of History (PoH)**:
    *   A novel mechanism developed by Solana that timestamps transactions before they are added to the blockchain. PoH improves efficiency and synchronization, making Solana faster than many other blockchains.
4.  **Energy Efficiency**:
    *   The design of Solana minimizes energy consumption, making it more environmentally friendly compared to energy-intensive blockchains like Bitcoin.
5.  **Smart Contracts and DApps**:
    *   Solana supports smart contracts, enabling developers to build decentralized applications like DeFi protocols, NFT marketplaces, and more.
6.  **Developer Ecosystem**:
    *   Solana offers tools and SDKs that simplify the development of blockchain-based applications, attracting a growing developer community.

* * *

### How Solana Works

*   **Proof of History (PoH)**:
    *   PoH provides a cryptographic timestamp for every transaction, enabling validators to order and process transactions efficiently.
*   **Tower BFT**:
    *   A consensus mechanism derived from Practical Byzantine Fault Tolerance (PBFT) that works in conjunction with PoH to achieve consensus quickly.
*   **Sealevel**:
    *   Solana's parallel processing engine enables multiple smart contracts to run simultaneously, improving efficiency and scalability.

* * *

### Key Metrics (as of recent updates):

*   **Transaction Speed**: Over 65,000 TPS.
*   **Block Time**: Approximately 400 milliseconds.
*   **Transaction Cost**: Typically less than $0.01 per transaction.

* * *

### Use Cases of Solana

1.  **Decentralized Finance (DeFi)**:
    *   Platforms like Serum and Raydium leverage Solana for fast and cost-effective trading.
2.  **Non-Fungible Tokens (NFTs)**:
    *   Solana hosts several NFT marketplaces, such as Magic Eden and SolSea.
3.  **Gaming and Web3 Applications**:
    *   Solana powers blockchain-based games and decentralized web applications.
4.  **Payments**:
    *   Low transaction fees make it ideal for microtransactions and payment services.

* * *

### Benefits of Solana

*   **High Speed and Efficiency**: Supports real-time, low-latency applications.
*   **Cost-Effectiveness**: Makes it viable for mass adoption and frequent transactions.
*   **Growing Ecosystem**: Active community and partnerships enhance its utility.

* * *

### Challenges and Criticisms

1.  **Centralization Concerns**:
    *   High hardware requirements for validators may limit decentralization.
2.  **Network Downtime**:
    *   Solana has experienced occasional outages due to high traffic or technical issues.
3.  **Competition**:
    *   Faces strong competition from blockchains like Ethereum, Binance Smart Chain, and Avalanche.

* * *

### Solana Indexer

Solana indexer consists of following parts:

1.  **Client**:
  *   The responsibility of this section is to interact with blockchain nodes for two purposes: to retrieve their blocks and to determine the latest Solana slot.
2.  **Indexer**:
  *   This section indexes Solana block in a desired format. The output of this section includes entities such as: Solana block, Solana native transfers and Solana token transfers. 

3.  **Datastore**:
  *   This segment stores the indexed data in a datastore. **MongoDB** is used as the datastore of this project. MongoDB is a popular **NoSQL database** that stores data in a flexible, JSON-like format called BSON. Unlike traditional relational databases, MongoDB uses a schema-less design, allowing for dynamic and hierarchical data structures, making it ideal for applications requiring scalability, high performance, and rapid development.
4.  **Graphql**:
  *   GraphQL is a query language and runtime for APIs that enables clients to request only the data they need, in the exact structure they want. Developed by Facebook, it allows developers to define a schema with strongly typed data and interact with it using a single endpoint, improving efficiency and flexibility compared to traditional REST APIs.

### Solana Indexer Health Check

1. **Logs**
 *   Read files in logs should be around the indexer depth that is set in docker compose
2. **Postman Api**
 *   `Get Latest Block` should be sufficient

### Solana Indexer Postman Test

1. Use `Get Latest Block` api.
2. In `Get Range of Block` set **sslot** and **lslot** in a way that they're both less that data.latestBlock.slot field in `Get Latest Block` response.
3. Get data.latestBlock.tokenTransfer.field.transactionHash in `Get Latest Block` response and put it in **txid** field in `Get Token Transfer By Transaction Hash`.
4. Get data.latestBlock.tokenTransfer.field.fromAddress in `Get Latest Block` response and put it in **fromAddress** field in `Get Token Transfer By From Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers.
5. Get data.latestBlock.tokenTransfer.field.toAddress in `Get Latest Block` response and put it in **toAddress** field in `Get Token Transfer By To Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers.
6. Get data.latestBlock.nativeTransfer.field.transactionHash in `Get Latest Block` response and put it in **txid** field in `Get Native Transfer By Transaction Hash`.
7. Get data.latestBlock.nativeTransfer.field.fromAddressin `Get Latest Block` response and put it in **fromAddress** field in `Get Native Transfer By From Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers
8. Get data.latestBlock.nativeTransfer.field.toAddress in `Get Latest Block` response and put it in **toAddress** field in `Get Native Transfer By To Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers