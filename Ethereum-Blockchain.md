Vitalik Buterin realized the need for a general-purpose programmable blockchain in Bitcoin. And in pursuit of this realization, he proposed a Turing complete scripting language on top of the Bitcoin blockchain forming Ethereum. blockchain-focused on storing the transaction details in an open public ledger whereas Ethereum is general-purpose programmable blockchain technology. Ether is the currency of Ethereum Blockchain. In Ethereum there is no limitation of cryptocurrency supply and also the transaction speed is 12 seconds.

**Ethereum World Computer:**

Ethereum’s vision is to create a single blockchain for the entire world calling Ethereum World Computer. Ethereum World Computer is a group of individual computers forming one massive computer. Each computer in the network will run a program called Ethereum Client. The Ethereum Client helps other systems to collaborate and form the Ethereum World Computer.

**Key Point:**

- Deterministic (Always give same output for same input)
- Isolation (Clients should run as isolated entities so no other client can disrupt EWC) 
- Terminability (Ethereum uses gas fees to ensure no smart contract enter into endless loop)

**Ethereum Virtual Machine**

EVM is “the runtime environment for smart contracts in Ethereum”. A smart contract is a self-executing program that resides in EVM. EVM enables smart contracts (EVM Code) to get executed on any operating system. It acts as a middle layer between the smart contract and the operating system. Also, it performs an essential role in Ethereum reading the code, computing transaction costs, executing transactions, etc.

![EvmArch__1_-1024x673](https://user-images.githubusercontent.com/80442960/221403195-041984a8-0ebb-47aa-b212-ea18e803eb83.png)

EVM got three storage areas:

1. **Storage**: Storage area pointed inside each account storing the contract state variables. The location is allocated during contract creation time.
1. **Memory**: The memory area holds temporary variables. Memory is only accessible during contract execution, and contents get discarded between calls.
1. **Stack**: Stack location used for storing intermediate values in computations. The stack doesn’t persist after contract execution.

Gas is the fee or pricing value used to execute a transaction on the Ethereum blockchain successfully.


**Ethereum World State**

The Ethereum world state is a mapping between address (160-bit identifiers for an account) and account states. It moreover, functions like a bank account that keeps track of the balance and customer spending.

![WorldState-1536x707](https://user-images.githubusercontent.com/80442960/221403236-367e4f84-e72f-41af-a557-ab0e9e673317.png)


**Gas:**

Gas refers to the unit that measures the amount of computational effort required to execute specific operations on the Ethereum network; usually represented in wei [10^(-18) eth], the smallest denomination of Ether.

**Accounts:**

An Ethereum account is an entry that can hold an ether balance, or send it to another account on the Ethereum blockchain network. These accounts can either be user-controlled know as Externally Owned Accounts or controlled by codes (contracts); termed as Contract Accounts.

![Screenshot-from-2021-11-03-10-08-33-1024x661](https://user-images.githubusercontent.com/80442960/221403282-d4a5e5cc-f626-443d-b615-9e402bc68359.png)

For externally owned accounts, the address is derived from the public key which is in turn derived from the private key. For contract accounts, the address is derived from the sender address (who has deployed the contract) and the nonce value associated with the sender address is the total number of transactions triggered from that account.

Ethereum accounts have four fields:

- **nonce** -- is a counter used to keep track of the number of transactions
- **balance** -- the number of Ether owned by the address, which is always specified in Wei.
- **codeHash** -- refers to the hash of the code associated with an account in the EVM. For EOA it is a hash of empty string.
- **storageRoot** -- The 256-bit hash of the root node of a Merkle Patricia Trie.

**Consensus:**

Ethereum switched its consensus mechanism from proof of work to proof of stake once the merge was complete on September 15, 2022. Under the proof of stake consensus, a group of validators are responsible for creating blocks.

**Beacon Chain:**

The Beacon Chain is the consensus engine of Ethereum 2.0. It randomly selects validators for a block based on a pseudorandom process called RANDAO and manages the consensus mechanism.

**Validator:**

One can become a validator by depositing 32 ETH using a specific transaction in the deposit contract in the Ethereum mainnet. The validators are responsible for creating new blocks (block proposer) and voting on a proposed block (committee). Validators are rewarded for honest behaviour and also penalized for dishonest behaviour.

**Proof of Stake (PoS):**

Time is divided into epochs, which are further sub-divided into 32 slots of 12 seconds each. Before the start of an epoch, each slot is assigned a validator as a block proposer, and a specific group of validators (minimum 128) called a committee. A validator can only be in one committee per epoch. There can also be more than one committee per slot. All the committees must be of same size.

During each slot, its block proposer will select a block to append to the existing chain, and the committee will vote to add this to the main chain. These votes are termed attestations and are weighted by the validator’s deposit. The validators broadcast their votes, and a block which gets a two-thirds majority of validator votes is accepted. The majority is decided based on the weight of deposits rather than the number of validators.

**Transaction Structure:**

Ethereum transaction has the following elements.

**nonce:**  Nonce in a transaction is a sequence number of transactions from an Ethereum account.

**gasLimit:** It is the maximum amount of gas units you are happy to spend on a specific transaction. 

**maxPriorityFeePerGas:** the maximum amount of gas to be included as a tip to the validator

**maxFeePerGas:**  the maximum amount of gas willing to be paid for the transaction (inclusive of baseFeePerGas and maxPriorityFeePerGas)

**to:** Destination account address; this is either an externally owned account (EOA) or a contract account.

**value:** It represents the amount of ether/wei from the sender to the receiver.

**data:** Data field is for contract activities (deployment or execution of the contract).

Transaction Fee (paid in ether)  = Gas Limit \*(Base fee + Tip)

Ethereum uses **Account Balance Model** for record keeping. In Ethereum, a global state stores a list of accounts with balances, code, and internal storage. Here a transaction is valid if the sending account has enough balance to pay for it. Under this case, the sending account is debited and the receiving account is credited with the value.







**Ethereum transaction Lifecycle:**

![TransactionFlowEthereumFinal](https://user-images.githubusercontent.com/80442960/221403318-ded6b0c2-ca03-40c5-8eac-076d3593ceb3.png)

**Decentralized Application (DApp):**

DApp is an application built on decentralized technology, rather than being built and controlled by a single, centralized entity or company. For instance, let’s take Google Pay. The payment app is built and controlled by a single company: Google. It is Google that defines the logic and conditions for running and processing your payment requests. However, with DApps, the control gets distributed and shared among the network participants. The business logic for DApps is embedded in a self-executing program called a smart contract that gets shared among the network participants. The smart contract is kept open and transparent that anyone can audit and change the instructions.

![DappVsApp-1024x362](https://user-images.githubusercontent.com/80442960/221403339-c7811d66-ceb7-4eb0-bf6b-7517b655fd1c.png)


**DApp Application Stack**

- UI
- Libraries & frameworks
- Wallets
- Smart Contracts
- Blockchain
- OS

In Ethereum, smart contracts are written in Solidity language.

**Web3:**

Web3 is a significant upgrade to the internet, nourishing with extra security, identity, trust, and user control layers. Web3-based protocols offer solutions to the Centralization, privacy, censorship, and ownership of digital goods which are also the advantages of Web3.

