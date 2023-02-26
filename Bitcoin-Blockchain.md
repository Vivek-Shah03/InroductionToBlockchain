**Types of Blockchain**

- Public blockchain
- Private blockchain
- Consortium blockchain

The white paper, Bitcoin: A Peer-to-Peer Electronic Cash System.

**Blockchain Features**

- Immutable
- Decentralized System
- Better Security
- Distributed Peer to Peer Network

**Note:**

- **Bitcoin** is a piece of software used for communication**.**
- **bitcoin** is a digital cryptocurrency used for transactions.
- **Blockchain** is an underlying technology running bitcoin.

**Components of Bitcoin Network**

- Software
- Cryptography
- Hardware
- Miners

**Type of Nodes**

- Full Node
- Light Node
- Miner Node
- Router Node

**Note:** The bitcoin’s total supply is 21 million. Bitcoin blockchain limits the size of a block by 1 MB.

**UTXO ( Unspent Transaction( Output )**

**Consensus**

- Voting based consensus (Ex: PBFT)
- Lottery based consensus (Ex: POW, POS)

**Note:**

To maintain the block creation time, the time is readjusted after every 2016th block. For example, if the block creation time is below 10 minutes, the threshold value will be decreased to increase difficulty. Likewise, if the block creation time is above 10 minutes, the threshold value will be increased to decrease difficulty.

**Forks:**

1. Hard Fork (Permanent Change)
1. Soft Fork (Temporary Change)

Mining nodes starts mining on top of the longest chain. The hash of the last block from the longest chain is added as the previous hash value in the newly created block. Eventually, the longest chain is accepted and the blocks in other chains is discarded.

![h](https://user-images.githubusercontent.com/80442960/221394781-ba5389f1-40fe-4efe-99db-a0dc9c2b6792.jpg)

To avoid situations of blocks getting discarded, the Bitcoin network suggests users to wait until six blocks are added on top of a block. Transaction is said to get confirmed if six blocks go after. In the above diagram, the branch ‘B2’ will be discarded, as it is not the longest chain. Such blocks are called Stale blocks. There is no reward for mining stale blocks. Occasionally there can be blocks with no valid parent block. These blocks whose parent blocks are not processed by the local nodes are known as Orphan blocks. When two blocks are mined within a small time interval and they are received in the opposite order, i.e. child before parent, orphan blocks are formed. The orphan blocks cannot be validated and they are stored in the orphan block pool until their parent block is received. They can be pulled from the orphan block pool and made part of the chain once the parent block is received.

**Note:** In the PoS system, blocks are forged or minted, not mined. The individuals validating the transactions, creating new blocks are called forgers.

**The Selection Criteria in POS:**

- Randomized block selection
- Coin age-based selection

**Que: Explain Nothing at stake problem in POS.**

**Variants of PoS**

- Delegated Proof of Stake
- Liquid Proof of Stake
- Bonded Proof of Stake
- Hybrid Proof of Stake





**Practical Byzantine Fault Tolerance**

PBFT works efficiently in the asynchronous system. It is optimized for low overhead time.

- Primary node send pre-prepare message to all nodes [ ID of the block, the block number, the primary view number, and the primary node’s ID]
- Each node send prepare message to every node [block ID, block number, node’s view number, and its ID]. Nodes must wait till they receive 2f+1 matching prepare messages from their peers, where f is the maximum number of faulty nodes allowed. Once the node gets 2f+1 prepare messages, the messages get added to their internal log.
- each node will send a commit message to the entire network including themselves. The commit messages contain the block ID, block number, node’s view number, and its ID. Just like the prepare phase, nodes wait until they receive 2f+1 matching commit messages. Once a node gets 2f + 1 matching commit messages, the messages get added to the log and the block gets committed to the blockchain.

Once the primary node finishes the committing phase, it will create a new block and repeat the process. After each view, a new node will be elected as the primary.

**What will happen if a node does not receive 2f+1 messages?** 

This means that the network failed to reach an agreement regarding the proposed block, implying more than f nodes in the network are faulty. There can also be scenarios where the primary node becomes faulty. In such cases, the network will fail to reach an agreement that will affect the working of the blockchain network. In order to prevent such scenarios, each view has a time period. If the network couldn’t reach an agreement within the view, any node in the network can request a view change. In the next view, a new node will be elected as primary and the process gets repeated.

**Variants of PBFT:**

RBFT (Redundant Byzantine Fault Tolerance) : Hyperledger Indy

IBFT: Quorum, Hyperledger Besu

SBFT (Speculative Byzantine Fault Tolerance) or Zyzzyva protocol: 

**Bitcoin Limitations:**

- Complex Architecture
- Uselessness of computation
- 51% Attack
- Slow transaction time (10 mins)
- High energy consumption
- Transaction finality (It is required for six confirmations (takes approx. 1 hour) in Bitcoin for a transaction to be final.)
- Limited Programmability

**Note:**

- Hyperledger Besu ==> POW, POS, POA
- Hyperledger Sawtooth ==> PBFT, POET

**Challenges of Blockchain:**

- Performance, Interoperability, Network Size, Human Error, Security flows
