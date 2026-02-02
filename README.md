# DIGDUG.DO — Protocol Repository

This repository contains the canonical protocol documentation for DIGDUG.DO.

It is not an application repository, a marketing site, or a collection of release notes. Its purpose is to define, explain, and preserve the invariant rules, semantics, and architectural principles of the DIGDUG.DO protocol as it evolves over time.

Readers should approach this repository as they would a protocol paper archive or a technical standard: as a source of truth against which implementations, interfaces, and public representations can be evaluated.

---

## How to Read This Repository

DIGDUG.DO is defined across several formal documents, each serving a distinct role. Together, they describe the protocol’s intent, mechanics, and constraints.

The **Whitepaper** provides the conceptual and architectural foundation. It explains why the protocol exists, how it separates execution from verification, how value is distributed deterministically, and how protocol truth is preserved independently of market conditions.

The **USDDD Monetary Policy** defines the economic rules governing USDDD. It specifies how supply is introduced, constrained, and released, and clarifies what USDDD is and is not. This document should be read as a monetary constitution rather than a feature description.

The **On-Chain Architecture** document describes the role of smart contracts, treasury custody, issuance boundaries, and upgrade discipline. It explains how on-chain state anchors protocol truth without attempting to encode the entire system on the blockchain.

The **Terminology Glossary** locks the meaning of language used throughout the protocol. Its purpose is to prevent semantic drift as the system evolves. Where ambiguity arises, the glossary is authoritative.

The **Genesis document**, where present, serves as a historical record. It captures protocol milestones and declarations and is not intended to be modified retroactively.

---

## Execution vs Verification

DIGDUG.DO deliberately separates execution from verification.

The **Terminal** is the execution surface. It is where users, sponsors, and operators perform protocol actions. The Terminal enforces participation rules and emits canonical protocol events, but it does not define protocol truth.

The **Scan** is the verification surface. It reconstructs protocol state by observing canonical ledgers, snapshot pricing data, and on-chain state. Scan is read-only with respect to protocol execution and is intended to serve as the public, authoritative reference for protocol metrics and state.

This separation allows interfaces and tooling to evolve without compromising auditability or economic integrity.

---

## Versioning and Protocol Phases

DIGDUG.DO evolves through explicit protocol phases that describe economic and governance posture. These phases are independent of software maturity and are declared deliberately.

Version identifiers encode phase, major changes, minor changes, and hotfixes. A change in phase represents a formal lifecycle transition and is treated as a protocol event rather than a routine release.

Terminal and Scan implementations may advance independently, but both are expected to reflect the same underlying protocol semantics as defined in this repository.

---

## What This Repository Is Not

This repository does not document UI behavior, API endpoints, deployment scripts, or operational procedures. It does not promise returns, describe market strategies, or provide trading guidance.

It also does not serve as a changelog for every software update. Only protocol-semantic changes are reflected in these documents.

---

## Source of Truth

In the event of disagreement between an interface, an announcement, or a third-party interpretation and the documents contained in this repository, the documents in this repository take precedence.

Protocol truth is defined by canonical ledgers, snapshot accounting, on-chain state, and the formal rules described herein.

---

## Closing Note

DIGDUG.DO is designed to remain intelligible over time. This repository exists to ensure that future readers can understand not only how the protocol works, but why it was built the way it was.

All implementations are expected to conform to the principles and constraints described here.

---

*End of README.*
