---
layout: default
title: Software Toolkits
---

Some of the key software toolkits we have developed are described below. Please see [our research pages](/research.html) for more.

## <a name="sfuzz"></a>sFuzz – Smart Fuzzing Contracts

In essence, smart contracts are computer programs which are automatically executed on a distributed blockchain infrastructure. Popular applications of smart contracts include crowd fund raising and online gambling, which often involve monetary transactions as part of the contract. Smart contracts in Ethereum are written in a programming language called Solidity. Like traditional programs, smart contracts written in Solidity may contain vulnerabilities, which potentially lead to attacks. The problem is magnified by the fact that smart contracts, unlike ordinary programs, cannot be patched once they are deployed on the blockchain.

**sFuzz** is a smart contract fuzzer which is based on and extends the well-known AFL fuzzer for C programs. It implements a novel adaptive searching strategy for maximizing the test coverage of smart contracts. It is the most efficient fuzzer Solidity/EVM smart contracts.

sFuzz is available for testing and evaluation at: [https://contract.guardstrike.com/#/scan](https://contract.guardstrike.com/#/scan)

A research version of sFuzz is available at [https://github.com/duytai/sFuzz](https://github.com/duytai/sFuzz). We welcome any enquiry and/or collaboration.

## <a name="pat"></a>PAT – Process Analysis Toolkit

**PAT** is a self-contained framework for to support composing, simulating and reasoning of concurrent, real-time systems and other possible domains. It comes with user friendly interfaces, featured model editor and animated simulator. Most importantly, PAT implements various model checking techniques catering for different properties such as deadlock-freeness, divergence-freeness, reachability, LTL properties with fairness assumptions, refinement checking and probabilistic model checking. To achieve good performance, advanced optimization techniques are implemented in PAT, e.g. partial order reduction, symmetry reduction, process counter abstraction, parallel model checking. So far, PAT has **3502+** registered users from **932+** organizations in **87 countries and regions**.

The main functionalities of PAT are listed as follows:

- User friendly editing environment (multi-document, multi-language, I18N GUI and advanced syntax editing features) for introducing models
- User friendly simulator for interactively and visually simulating system behaviors; by random simulation, user-guided step-by-step simulation, complete state graph generation, trace playback, counterexample visualization, etc.
- Easy verification for deadlock-freeness analysis, reachability analysis, state/event linear temporal logic checking (with or with fairness) and refinement checking.
- A wide range of built-in examples ranging from benchmark systems to newly developed algorithms/protocols.

The latest version of PAT can be downloaded from the main website at: [https://pat.comp.nus.edu.sg/](https://pat.comp.nus.edu.sg/)
