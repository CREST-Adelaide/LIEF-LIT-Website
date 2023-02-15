---
layout: page
title: LIT Blockchain
subtitle: Blockchain-enabled Tasking of IoT testkits
---

# Context

The Adelaide IoT testbed is made up of multiple sets of IoT test kits, which can be adapted to different types of studies and deployed in different environments. It also aims to accompany the testkits from third parties. Such a distributed testbed benefits from a trustworthy and decentralised platform for managing the tasking and deployment of IoT hardware kits. The purpose of the LIT Blockchain is to provide such a platform. 

# Design and implementation

The LIT blockchain, abbreviated as LIT, is a blockchain-based system comprising 3 main parts.

### LIT Core

The core part of LIT is comprises two smart contracts, which are software components existing within and operated by a blockchain. These smart contracts implements the logic regarding the tasking of IoT test kits. They are invoked by both end-users (researchers and system admins) and the LIT Middleware components described below. 

All interactions with the LIT Core are validated and stored by the blockchain. These records form the foundation of the trustworthiness in tasking and orchestration by LIT.

### LIT Middleware

LIT Middleware is deployed on Raspberry Pi, acting as the gateway between wireless sensors and the rest of an IoT test kit. The middleware is responsible for interacting with the LIT Core on behalf of the sensors. It also responds to the tasking requests from the LIT Core.

### LIT Frontend

LIT Frontend is a web-based interface that enable end users to interact with the LIT Core smart contracts to issue tasking requests and retrieve experiment results. 

# Resources

- [Source Code and Architecture](https://github.com/CREST-Adelaide/LIEF-LIT-Blockchain)