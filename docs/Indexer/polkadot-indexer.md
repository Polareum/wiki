# Polkadot Blockchain Indexer

Polkadot is a multi-chain, interoperable blockchain network designed to enable different blockchains to interconnect and communicate with each other. Its goal is to address the limitations of traditional blockchains, which typically operate in isolation from one another, by allowing them to share information and collaborate.
Polkadot was created by **Dr. Gavin Wood**, co-founder of Ethereum and former CTO of the Ethereum project. It was developed by the **Web3 Foundation** and **Parity Technologies**.

### Key Features of Polkadot:

1.  **Interoperability**: Polkadot facilitates communication between different blockchains, allowing them to send messages and exchange data seamlessly. This enables cross-chain interactions and the transfer of assets and information.
    
2.  **Relay Chain**: The main chain in Polkadot, known as the **Relay Chain**, coordinates the network's activities. It does not support smart contracts but provides security and consensus for the entire network. The Relay Chain acts as the backbone of the system.
    
3.  **Parachains**: Polkadot supports **parachains**, which are independent blockchains that run in parallel to the Relay Chain. Each parachain can be customized to meet specific use cases, and they can interact with other parachains through the Relay Chain. Parachains benefit from the shared security and interoperability provided by Polkadot.
    
4.  **Shared Security**: One of the key innovations of Polkadot is its **shared security model**. The Relay Chain provides security to the parachains, so they don't need to secure themselves individually. This makes it easier for new blockchains to join the network without worrying about security concerns.
    
5.  **Governance**: Polkadot has an on-chain governance system that allows token holders to participate in decision-making. This includes voting on protocol upgrades and the allocation of resources. The governance system is designed to be decentralized and transparent.
    
6.  **Nominated Proof of Stake (NPoS)**: Polkadot uses a **Nominated Proof of Stake** consensus mechanism. Validators are selected based on the amount of DOT (Polkadot's native cryptocurrency) they stake, and they are responsible for securing the network. Nominators can also participate by staking DOT to back trusted validators.
    
7.  **Scalability**: By supporting parallel blockchains (parachains), Polkadot aims to achieve better scalability compared to single-chain networks. The network can process multiple transactions simultaneously, allowing it to handle more transactions and grow more efficiently.
    

### Polkadot’s Ecosystem:

Polkadot has seen the development of a growing ecosystem of projects and applications that are building on the network. These include decentralized finance (DeFi) platforms, decentralized applications (dApps), and other blockchain projects that leverage Polkadot's interoperability and scalability.

### The DOT Token:

The native cryptocurrency of Polkadot is called **DOT**. It serves several key purposes:
*   **Governance**: DOT holders can vote on decisions affecting the network.
*   **Staking**: DOT is used for staking, which secures the network through validators.
*   **Bonding**: DOT is also used to "bond" new parachains to the network, ensuring their participation and security.

### Polkadot's extrinsics

In Polkadot, **extrinsics** are operations or transactions that change the state of the blockchain. They are actions initiated by an external actor (such as a user, dApp, or validator) to modify the blockchain’s state, such as transferring tokens, submitting a governance proposal, or staking. Essentially, **extrinsics** represent any action that is sent to the blockchain for processing and execution.

### Polkadot’s Events:

In the context of Polkadot, **Events** are a mechanism for logging and communicating important occurrences or actions within the blockchain. They allow various parts of the network to generate and record events that provide information about specific actions that take place in the blockchain ecosystem.

**Key Features of Events in Polkadot**:

1.  **On-chain Logging**: Events are generated and stored on-chain, which means they are permanently recorded in the Polkadot blockchain’s state. These logs can be accessed and queried by anyone interacting with the blockchain, such as external dApps, users, and validators.
    
2.  **Event System**: Polkadot’s event system is decentralized and is integrated with the **Substrate** framework (on which Polkadot is built). Substrate provides an event-handling system that can be used by parachains and the Relay Chain to emit events.
    
3.  **Event Emission**: When specific actions or transactions are processed on the network (e.g., a token transfer, a governance proposal being passed, or a parachain slot auction taking place), corresponding events are emitted. These events typically include information about the action, such as the actor (e.g., sender, recipient), the amount of data or assets involved, and the resulting change in the state.
    
4.  **Event Types**: Different types of events can be emitted based on the actions happening within the system. Examples include:
    *   **Transaction Events**: Such as a successful transaction or failure (e.g., when a transfer of tokens is processed).
    *   **Governance Events**: For example, when a governance proposal is passed or rejected.
    *   **Parachain Slot Events**: Emitted during the process of parachain slot auctions or when parachains are added or removed.
    *   **Validator Events**: These could include events related to staking or the activation/deactivation of validators.
5.  **Listening to Events**: dApps, services, or other blockchain components can listen for specific events to trigger actions or behaviors. For example, a decentralized application (dApp) might listen for the event of a user transferring tokens and then update the user interface accordingly.
    
6.  **Efficiency**: Events are designed to be lightweight and efficient. Since they are just logs of specific actions or changes, they don’t require significant computation to generate, making them a fast way to record state changes.
    
### Polkadot Indexer

Polkadot indexer consists of following parts:

1.  **Client**:
  *   The responsibility of this section is to interact with blockchain nodes for two purposes: to retrieve their blocks and to determine the latest Polkadot block number.
1.  **Indexer**:
  *   This section indexes Polkadot block in a desired format. The output of this section includes entities such as:  Polkadot block, transfers, non transfer extrinsics and events.
3.  **Datastore**:
  *   This segment stores the indexed data in a datastore. **MongoDB** is used as the datastore of this project. MongoDB is a popular **NoSQL database** that stores data in a flexible, JSON-like format called BSON. Unlike traditional relational databases, MongoDB uses a schema-less design, allowing for dynamic and hierarchical data structures, making it ideal for applications requiring scalability, high performance, and rapid development.
1.  **Graphql**:
  *   GraphQL is a query language and runtime for APIs that enables clients to request only the data they need, in the exact structure they want. Developed by Facebook, it allows developers to define a schema with strongly typed data and interact with it using a single endpoint, improving efficiency and flexibility compared to traditional REST APIs.

### Polkadot Indexer Health Check

1. **Logs**
 *   Read files in logs should be around the indexer depth that is set in docker compose
2. **Postman Api**
 *   `Get Latest Block` should be sufficient

### Polkadot Indexer Postman Test

1. Use `Get Latest Block` api.
2. In `Get Range of Block` set **sBlock** and **lBlock** in a way that they're both less that data.latestBlock.blockNumber field in `Get Latest Block` response.
3. Get data.latestBlock.transfers.extrinsicHash in `Get Latest Block` response and put it in **extrinsicHash** field in `Get Transfer By Extrinsic Hash`.
4. Get data.latestBlock.transfers.fromAddress in `Get Latest Block` response and put it in **fromAddress** field in `Get Transfer By From Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers.
5. Get data.latestBlock.transfers.toAddress in `Get Latest Block` response and put it in **toAddress** field in `Get Transfer By To Address`, **limit** shows how many transfers you want to get and **skip** field skip over transfers.
6. Get data.latestBlock.nonTransferExtrinsics.transactionHash in `Get Latest Block` response and put it in **extrinsicHash** field in `Get  Non Transfer Extrinsic`.