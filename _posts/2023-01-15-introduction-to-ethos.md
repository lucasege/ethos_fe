---
title: "Introduction to Ethos"
layout: post
date_string: MONDAY. JANUARY 15, 2023
image: /assets/images/ethos-article-cover-image.jpg
headerImage: false
category: blog
description: Ethos is the coordination layer that is bringing Ethereum restaking to Cosmos. Appchains can now benefit from the increased economic security of Ethereum and have access to the largest node operators in the ecosystem, all on one platform.
---

Ethos is the coordination layer that brings Ethereum restaking to Cosmos. Appchains can now benefit from the increased economic security of Ethereum and have access to the largest node operators in the ecosystem, all on one platform.

### Background

Within Cosmos, there are currently two main ways to launch an appchain. The first is bootstrapping a sovereign validator set from scratch. This requires significant BD effort from the protocol teams to convince node operators to join from genesis, which oftentimes also leads to high inflation of the native token to subsidize validators. In addition, the protocol may suffer from low economic security as the native token and application initially attempt to gain traction. 

A second option would be integrating [ICS replicated security](https://cosmos.github.io/interchain-security/) and adopting the validator set of the Cosmos Hub. Doing so requires passing a governance proposal with the Cosmos Hub, and sharing a large percentage of protocol generated revenue with the Cosmos Hub validators. This lack of expressivity over tokenomics and other protocol decisions makes this an unfavourable option for some developers. Validators suffer as well by being forced to validate any replicated chains on top of the selected provider chain. This increases node hardware requirements and subjects them to asymmetric downsides, as well as many other risk factors.

A third emerging solution is Mesh Security, which was first popularised by Osmosis, Juno, Confio and others, whom we take great inspiration from.
> Take Chain A (provider chain) with native staking token A and similarly for Chain B (consumer chain). Mesh Security is when A can be used as a staking asset on Chain B in addition to B. This increases Chain B's economic security from $$0.66 \times MCAP(B)$$ to $$0.66 \times (\text{MCAP}(B) + \lambda \text{MCAP}(A))$$. Where $$\lambda$$ is the preset *virtual* limit of A on Chain B. There is no new addition of nodes, the additional economic stake is *virtually* delegated to the existing node operators on Chain B. This can also be called cross-staking or a specific form of superfluid staking.

<div style="text-align: center;">
<img src="/assets/images/mesh.jpg" alt="Mesh Diagram" style="width:75%;">
</div>

### Mission Statement

From the above description, one can discern that Mesh Security solves most of the flaws of replicated security and a sovereign validator set. This is because appchains can always change the degree of "shared security" they need by changing &lambda;. They can benefit from having high economic security from launch as well as have sovereignty over protocol decisions as the appchain still maintains its own validator set. It is therefore our view that Mesh Security is the **superior** shared security solution and this is one of our core beliefs at Ethos. 

Another fundamental conviction we have is that EigenLayer will be the premier venue for shared security with restaked ETH being the most coveted asset for DeFi & protocol integrations. EigenLayer has now reached $1B in cumulative deposits and given that Ethereum has $66B in staked assets, we believe that this number will grow exponentially as launch comes soon. We expect EigenLayer deposits to surpass ATOM and other Cosmos native assets in terms of market cap. 
 
It is also our mission to break down the silos between the Ethereum and Cosmos ecosystems. Within crypto, Ethereum has proven to be the strongest asset, with the deepest liquidity moats and highly decentralized validator sets. Cosmos shines as a dynamic space for innovation, fostering the growth of pioneering ideas and delivering exceptional application experiences. We aim to lower the barriers of connectivity between these two ecosystems and bring net positive outcomes to all stakeholders.  

### Architecture Overview

The technical infrastructure of Ethos spans both the Ethereum and Cosmos ecosystems. To handle the restaking of ETH and associated slashing mechanisms we leverage the infrastructure of EigenLayer by deploying an AVS (Actively Validated Service). As for the mesh security contracts we rely on IBC and our own Ethos appchain to coordinate users' stake between consumer chains.  

<div style="text-align: center;">
<img src="/assets/images/ethos-diagram.jpg" alt="Ethos Diagram" style="width:75%;">
</div>

EigenLayer restakers deposit staked ETH into an AVS on ETH L1 and choose an operator to delegate to while doing so. Each EL operator has a preset chosen validator on each of the Cosmos consumer chains to delegate their *virtual* stake. The Ethos appchain then coordinates this updated state to the respective consumer chains via IBC and handles the subsequent rewards and/or slashing updates. These are both reflected in the AVS contract on ETH L1 through an off-chain relayer mechanism. 

### What's next

We are currently in a private testnet phase and are focussed on bringing  new consumer chains to integrate Ethos mesh security. If you are one of these consumer chains or want to discuss any of the above topics, feel free to reach out to us via [Twitter](https://twitter.com/EthosStake) or [email](mailto:info@ethosstake.com)! 