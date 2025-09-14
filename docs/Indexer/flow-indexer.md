# Flow Blockchain Indexer

Flow is a fast, decentralized, and developer-friendly blockchain designed for creating and scaling digital assets and applications, particularly focused on gaming, NFTs (Non-Fungible Tokens), and other high-performance decentralized applications (dApps). It was developed by Dapper Labs, the team behind CryptoKitties.

## Key Features

### 1. **Scalability Without Sharding**
   - Flow achieves scalability by using a unique multi-role architecture that separates the work of validating transactions and producing blocks across four different node types. This allows for efficient scaling without the need for sharding, which is often complicated and difficult to implement in other blockchains.

### 2. **Developer-Friendly Environment**
   - Flow provides an easy-to-use, developer-focused ecosystem, making it simple to build smart contracts, dApps, and digital assets.
   - The primary programming language for Flow is **Cadence**, a resource-oriented programming language designed specifically for creating smart contracts and digital assets on the Flow blockchain.

### 3. **High Throughput and Low Latency**
   - Flow is designed to handle a high number of transactions per second (TPS) with low latency. This makes it ideal for applications that require real-time processing, such as gaming and NFTs.
   - It can process thousands of transactions per second without compromising on decentralization or security.

### 4. **User and Developer-Friendly Tools**
   - Flow provides several tools and services, including a comprehensive SDK, libraries, and APIs for developers to create decentralized applications.
   - It also offers easy integration for users to interact with the blockchain, making it easy to use, even for non-technical users.

### 5. **NFT Support**
   - Flow was specifically built with NFTs in mind. It has a powerful and efficient system for creating, buying, and selling NFTs.
   - The network allows for the minting of unique tokens with rich metadata, enabling NFTs to have higher utility and value in games, collectibles, and other digital ecosystems.

## Flow Blockchain Components

### 1. **Nodes**
   - Flow uses a multi-role node architecture with four distinct roles:
     1. **Collection Nodes**: Responsible for collecting transactions.
     2. **Consensus Nodes**: Validate and achieve consensus on the blocks.
     3. **Execution Nodes**: Execute the logic of smart contracts.
     4. **Verification Nodes**: Verify the results of transactions and store data.
   
   This unique architecture helps Flow scale effectively by allowing each node type to specialize in one aspect of the blockchain process.

### 2. **Flow Token (FLOW)**
   - The **FLOW** token is the native cryptocurrency of the Flow blockchain. It serves several purposes, including:
     - **Transaction fees**: Used to pay for transaction fees on the network.
     - **Staking**: Validators must stake FLOW tokens to secure the network and participate in consensus.
     - **Governance**: FLOW token holders can vote on protocol upgrades and network governance.

### 3. **Cadence Programming Language**
   - **Cadence** is a resource-oriented programming language designed for the Flow blockchain. It enables the creation of safe and secure smart contracts and digital assets.
   - Cadence allows developers to easily define digital assets, such as NFTs, and manage their lifecycle (e.g., minting, transferring, burning).

### 4. **Smart Contracts**
   - Flow allows developers to write and deploy smart contracts on the blockchain using Cadence. These smart contracts are executed on Flow’s execution nodes, which handle the logic and state changes required for dApps and NFTs.

## Use Cases

### 1. **NFTs and Digital Collectibles**
   - Flow is particularly well-known for its use in the **NFT space**. Major projects such as **NBA Top Shot** and **CryptoKitties** are built on Flow.
   - NFTs on Flow are scalable and can represent various digital assets, from art and music to game items and digital collectibles.

### 2. **Gaming**
   - Flow is optimized for gaming applications, enabling game developers to create in-game economies that allow for seamless and secure transactions of digital goods, such as in-game assets, skins, and characters.
   - The blockchain’s low transaction fees and high throughput are key factors for making Flow a viable solution for gaming.

### 3. **Decentralized Finance (DeFi)**
   - Flow can also be used to power decentralized finance (DeFi) applications, offering fast and secure ways to trade, lend, and borrow digital assets without relying on intermediaries.

### 4. **Digital Identity and Data Ownership**
   - Flow enables individuals to have full control over their digital identities and personal data. It also supports privacy-focused applications that empower users to share data selectively while maintaining ownership and control.

### 5. **Governance**
   - With its native token FLOW, the network supports decentralized governance, allowing users to propose and vote on protocol changes and upgrades, ensuring that the network evolves according to the needs of its community.

## Advantages of Flow

- **Scalable Architecture**: Flow can process high volumes of transactions without compromising on performance.
- **Developer-Focused**: The ecosystem includes easy-to-use tools and a custom programming language (Cadence) for building dApps.
- **Optimized for NFTs**: Flow is specifically designed to handle NFTs and digital collectibles, offering fast transaction times and low costs.
- **Low Transaction Fees**: Flow has extremely low fees compared to other blockchains, making it ideal for microtransactions and large-scale applications.

## Flow Indexer Health Check

1. **Logs**
 *   Read files in logs should be around the indexer depth that is set in docker compose
2. **Postman Api**
 *   'Get Latest Block' should be sufficient

## Flow Indexer Postman Test

1. Use 'Get Latest Block' api.
2. In 'Get Range of Block' set sBlock and lBlock in a way that they're both less that data.latestBlock.blockHeight field in 'Get Latest Block' response.
3. Get data.latestBlock.transactions.transactionHash in 'Get Latest Block' response and put it in transactionHash field in 'Get Transfer By Transaction Hash'.
4. Get data.latestBlock.transactions.events.from in 'Get Latest Block' response and put it in fromAddress field in 'Get Transfer By From Address', limit shows how many transfers you want to get and skip field skip over transfers.
5. Get data.latestBlock.transactions.events.To in 'Get Latest Block' response and put it in toAddress field in 'Get Transfer By To Address', limit shows how many transfers you want to get and skip field skip over transfers.