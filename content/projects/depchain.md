---
title: "DepChain — Permissioned Blockchain with BFT Consensus"
description: "Permissioned blockchain implementing the Basic HotStuff BFT consensus over UDP, with a layered link stack (FairLoss → Stubborn → Authenticated Perfect Links via X25519 DH + HMAC), BLS threshold-signed Quorum Certificates, EVM execution via Hyperledger Besu, and a frontrunning-resistant ERC-20 token. Tolerates f = ⌊(n−1)/3⌋ Byzantine replicas."
tech_stack:
  - "Java"
  - "Hyperledger Besu"
  - "Solidity"
  - "UDP"
  - "BLS"
  - "Ed25519"
live_url: "https://github.com/LuisAPR1/Permissioned-Blockchain-with-BFT-Consensus"
live_label: "View on GitHub"
group: "Distributed Systems & Backend"
weight: 20
---

<div class="mt-8">

DepChain is an end-to-end permissioned blockchain system I built for the **Highly Dependable Systems** course at IST. The system tolerates `f = ⌊(n-1)/3⌋` Byzantine replicas while still settling transactions and executing arbitrary smart contracts.

## What I built

### Consensus layer (Basic HotStuff over UDP)

I implemented the **Basic HotStuff** Byzantine Fault Tolerance algorithm from scratch on top of unreliable networks:

- A layered link stack: `FairLossLink → StubbornLink → AuthenticatedPerfectLink` over UDP.
- **Authenticated Perfect Links** with an ephemeral X25519 Diffie-Hellman handshake (signed with Ed25519) deriving per-session HMAC keys.
- **Quorum Certificates** secured with **BLS threshold signatures** via the JPBC pairing-based crypto library, so a single 48-byte signature attests `2f+1` votes.
- Three-phase HotStuff (`PREPARE → PRE-COMMIT → COMMIT → DECIDE`) with leader rotation and view changes.

### Transaction processing engine

On top of consensus I built a full transaction engine:

- **Genesis loading** with deterministic world-state snapshot/restore, so a crashed replica recovers to a consistent state.
- **Mempool** ordered by gas price, nonce, and gas cap.
- **EVM execution** integrated through **Hyperledger Besu**, executing arbitrary Solidity bytecode with a custom gas-fee mechanism.
- **DepCoin** native transfers with overspend, double-spend, and replay protection.
- **Block persistence** with crash-recovery round-trip tests.

### IST Coin (frontrunning-resistant ERC-20)

I designed and shipped an ERC-20 token whose `approve()` function is redesigned to prevent the classic **Approval Frontrunning attack** — a known problem with naive ERC-20 implementations where an attacker can front-run a balance change to an allowance.

### Test surface

The project ships with **45 JUnit 5 tests** covering:

- Link-stack correctness (stubborn delivery, perfect-link rejection of wrong keys)
- HotStuff data structures (`TreeNode`, `Message`, `QC`)
- Crypto primitives (Ed25519, BLS threshold, QC integration)
- Full 4-replica consensus over UDP
- Crash tolerance and silent-Byzantine fault injection
- Spoofing, overspend, replay, double-spend, frontrunning attack scenarios

### Why it matters

Building DepChain meant doing distributed-systems engineering across the whole stack: cryptography, networking, consensus, virtual-machine integration, and adversarial testing. The result is a system that's not just "it compiles" but actually demonstrably tolerant to crashes and Byzantine peers under fault injection.

</div>
