# General Grant Proposal

**Subscript:** substrate smart contact written in `AssemblyScript`

## Project Overview :page_facing_up:

We are intergrating assemblyscript into substrate smart contract which is similar to ink. It involve buillding substrate contract runtime api, builtin modules, and development sdk. we name the language and sdk as `Subscript`.

### Overview

**Subscript** is a smart contract language written in AssemblyScript for substrate based chain. We will provide essential substrate api and builtin tools to support contract development.

Similar to parity ink, `Subscript` is built on top of  AssemblyScript and follow all AssemblyScript syntax. Subscript is more like a development kit with some builtin module and tools. As assemblyscript is easy to interact with TypeScript and JavaScript, `Subscript` is much more friendly for dapp developers.

### Project Details

**Subscript** is designed as standard AssemblyScript with builtin contract api. First of all, `Subscript` libray  will provide  basic `contract` pallet runtime api access.

* contract runtime envionment
* contract `memory` management
* state storage access, set and get value by key.
* `event` data generation and storage

The `Subscript` library also add support for contract interaction utilties, including:

* contract metadata generator
* basic data structure: dynimic array, map, list,
* user struct storage layout
* `account` and  `balance` interface 
* contract call abstraction
* builtin utility fuctions

The package will provide contract template and intergation tool with substrate node. 

There is no plan for `EVM Pallet` support.

### Ecosystem Fit
Some of the function of `Subscript` are similar to LimeChain's work of AssemblyScript Runtime, but they are  made for different scenario. LimeChain AssemblyScript Runtime focus on building substrate runtime with wasm compiled from AssemblyScript. It involves building all the substrate runtime environment entry with AssemblyScript and other basic library. `Subscript` aims to implement all the substrate smart contract low level interface with AssemblyScript. `Subscript` also add support for basic contract lib and project template for easy development.  We may benefit  previous work from LimeChain such as `SCALE`codec, runtime entry implemention.

## Team :busts_in_silhouette:

### Team members
* Symon Ho: Leading consensus R&D and engineering in multichain system. Prior to that, developer of openstack project,  engaged in performance tools and  monitoring  system for cloud platform.
* Ice Min: 10+ years experience in c/c++ development, real time database products and digital currency transaction platform products expert. Developer of BitCoin and Ethereum wallet.

### Team Website
* https://github.com/slickup

### Team's experience

We implemented the fruitchain consensus integated with ethereum, and used pbft to provide finalization in blockchain system.  Fruitchain mainnet launched in 2019 and privide 500+ TPS for transaction validation.

We alse engaged in smart contract tools interaged with vyper for contract audit and testing. 

### Team Code Repos
* https://github.com/slickup/subscript

## Development Roadmap :nut_and_bolt:

### Overview
* **Total Estimated Duration:** 4 - 6 month
* **Full-time equivalent (FTE):**  2
* **Total Costs:** $60k.

### Milestone 1  — Implement smart contract low level api
* **Estimated Duration:** 2 month
* **FTE:**  2
* **Costs:** $20,000

In this milestone, all the basic contract runtime compoment will be implemented. This stage will establish a runtime environment for smart contract. We may benefit from the refrence implemention of parity Ink and provide similar api.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Testing | This milestone will have unit-test for all the following runtime api impemented. We will mock most of the contract runtime api to simulate host functions. Integration test will be delivered in next milestone. |
| 1. | contract runtime environment | contract builder and execution to initailize the contract code |
| 2. | core types | add core component: AccountId, Balance, Hash, Block |
| 2. | storage access | contract low level storage read and write with key |
| 3. | object packing utilty | User data structure packing and unpacking method to storage access. |
| 4. | memory manipulation | memory make and getter, setter |
| 5. | contract event generation | Generate event from contract call |
| 6. | ontract call method | Method for make contract call. |
| 7. | hash utility | Make digest of encoded input to generate hash image |
| 8. | `SCALE` codec | Builtin codec functions to serialize and deserialize input.we may directly use LimeChain `as-scale-codec` implementation. |

### Milestone 2 Language and contract core component

* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $12,000

In this milestone, the language component with contract will be privided to write contract code. Both language function and building tool will be added into the development kit.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 1. | npm template | Provide a script tool to bootstrap a assemblyscript contract template and initialize project |
| 2. | contract metadata | Generate smart contract metadata with builtin module |
| 3. | use data structure layout | Pack and unpack user defined structure to state stroage |
| 4. | contract initialize function | Function to initialze contract code and state |
| 5. | contract call method | Method for calling other contract. |

### Milestone 3 Builtin fucntions and supporting lib

* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $12,000

In this milestone, we will launch language builtin fucntions and essential libary. 

From this milestone, we can demonstrate full substrate contract example written in AssemblyScript.

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 1. | container data structure | Builtin container type to store user defiine sturcture, including dynamic vector, list, mapping |
| 2. | decorator for contract api access | Add decorator to encapsulate contract api interaction |

### Milestone 4 Packaging and integation with substate node

* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $8,000

In this milestone, we will launch language builtin fucntions and essential libary

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 1. | npm template | Provide a script tool to bootstrap a assemblyscript contract template and initialize project |
| 2. | integration with substrate node | substrate commands to deploy and call  `Subscript` compiled contract with substate node |
| 3. | npm testing tool | debug and test tool to interact with substate contract |

### Milestone 5 Website for `Subscript` document and tutorial

* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $8,000

In this milestone, we will launch the `Subscript` website to show documents and Tutorial

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 1. | `Subscript` website | A website to introduce `Subscript` feature and use case |
| 2. | public documents | Documents for language detail and implemention |
| 3. | tutorials | Tutorials dive into the language feature and development |
| 3. | `Subscript` example | Examples to demonstrate `Subscript` contacts and application. |


## Future Plans
After the `Subscript` presentation , we may make our effort to bring more  tool for contract development.

A simulated contract sandbox similar to ganache is needed to debug and test contract.

We may add more intergated tool and IDE packge for contract developer.

## Additional Information

We expect any developer who is interested in AssemblyScript smart contract join us and build efficient framework.
