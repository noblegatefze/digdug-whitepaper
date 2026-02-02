# DIGDUG.DO TERMINOLOGY GLOSSARY  
Authoritative Definitions for Protocol Semantics

---

## Purpose of This Glossary

This glossary defines the authoritative meanings of terms used throughout the DIGDUG.DO protocol, its documentation, and its public communications. The purpose of this document is to prevent semantic drift, narrative reinterpretation, and ambiguity as the protocol evolves.

Where a term is defined here, that definition supersedes informal, colloquial, or external interpretations. Changes to definitions in this glossary constitute protocol-semantic changes and must be treated with the same rigor as changes to monetary or on-chain policy.

---

## DIGDUG.DO

DIGDUG.DO is a deterministic protocol for verifiable value distribution and fuel-governed participation. The term refers to the protocol as a whole, including its accounting model, on-chain components, execution surfaces, and verification surfaces. It does not refer to a single application, interface, or company.

---

## Protocol

The protocol is the set of rules, constraints, and deterministic processes that govern how value is distributed, accounted for, and verified within DIGDUG.DO. The protocol exists independently of any specific user interface or implementation detail.

---

## Terminal

The Terminal is the execution surface of the protocol. It is the environment in which users, sponsors, and operators initiate protocol actions. The Terminal enforces participation constraints and produces canonical protocol events. The Terminal does not define protocol truth and is not an authoritative source of metrics or state.

---

## Scan

Scan is the verification and observation surface of the protocol. It reconstructs protocol state by reading canonical ledgers, snapshot pricing data, and on-chain state. Scan does not execute actions or mutate protocol state. Metrics published by Scan are considered authoritative representations of protocol truth.

---

## Action

An action is a protocol-relevant event initiated through the Terminal that consumes fuel, triggers accounting changes, or contributes to distribution logic. Actions are recorded in canonical ledgers and form the foundational inputs to protocol accounting.

---

## Canonical Ledger

A canonical ledger is an append-only record that represents the authoritative history of a specific class of protocol events. Canonical ledgers are used to derive all higher-order metrics and must be sufficient for independent reconstruction of protocol state.

---

## Claim

A claim is a canonical record representing value earned or owed as a result of protocol activity. Claims are explicit protocol objects and are not inferred from wallet balances or UI state. Claims may be settled, unsettled, or pending according to protocol rules.

---

## Distribution

Distribution refers to the process by which the protocol assigns value to participants based on canonical claims. Distribution is accounted for deterministically using snapshot valuation and is independent of real-time market prices.

---

## Snapshot Pricing

Snapshot pricing is the method by which the protocol assigns reference USD values to assets at defined time windows. Snapshot prices are used exclusively for internal accounting and metric derivation and are not intended to represent market price.

---

## Value Distributed

Value distributed is the aggregate USD reference value of claims within a given window, computed using snapshot pricing. It is a protocol accounting metric, not a measure of realized market profit.

---

## Fuel

Fuel is the abstract unit of protocol cost that governs participation and limits abuse. In DIGDUG.DO, fuel is denominated in USDDD. Fuel consumption is recorded canonically and is used to measure protocol efficiency.

---

## USDDD

USDDD is the internal protocol fuel and accounting unit of DIGDUG.DO. It is designed to meter participation, anchor accounting, and enforce protocol constraints. USDDD is not designed as a speculative asset or a promise of return.

---

## Mint-on-Withdraw

Mint-on-withdraw is the issuance model under which USDDD enters circulating supply only at the moment a participant executes a withdrawal. Prior to withdrawal, USDDD may exist as accounted entitlement without contributing to circulating supply.

---

## Circulating Supply

Circulating supply refers to the total amount of USDDD that has been minted on-chain and is freely transferable under protocol rules. Circulating supply does not include accounted entitlement that has not yet been withdrawn.

---

## Fund Network

The Fund Network is the protocol subsystem through which participants obtain USDDD entitlement by depositing capital under defined rules. The Fund Network does not guarantee returns and operates according to deterministic accounting and accrual reference logic.

---

## Accrual Reference

The accrual reference is a bounded protocol signal derived from canonical accounting that expresses the relationship between value distributed and fuel consumed over time. It is informational and does not constitute a yield, promise, or obligation.

---

## Applied Accrual

Applied accrual is the accrual reference after protocol-defined bounds and scaling have been applied. It is used for protocol display and internal logic but does not guarantee outcomes.

---

## Phase

A phase is a protocol lifecycle designation describing economic and governance posture. Phases are declared explicitly and are not inferred from software version numbers alone.

---

## Zero Phase

Zero Phase is the initial operational phase of DIGDUG.DO in which the protocol is live and verifiable while operating under constrained economic freedoms.

---

## Genesis Phase

Genesis Phase is a formally declared lifecycle phase representing a transition in protocol posture and economic openness. It is distinct from Genesis State.

---

## Genesis State

Genesis State is a contract-level capability flag that enables specific on-chain mechanics required for protocol operation. Activation of Genesis State does not, by itself, indicate a phase transition.

---

## Version

A version is a structured identifier describing protocol evolution. In DIGDUG.DO, the leading digit of the version encodes the protocol phase, while subsequent digits encode major, minor, and hotfix iterations.

---

## Wallet Role

A wallet role is a functional designation assigned to an on-chain address or contract, such as treasury custody, fund network operations, liquidity operations, or administrative control. This glossary defines roles rather than addresses to preserve forward compatibility.

---

## Treasury

The Treasury refers to protocol-controlled custody roles responsible for holding and managing assets according to explicit protocol rules. The Treasury does not autonomously issue or destroy supply.

---

## Pipe

A pipe is a conceptual on-chain or accounting pathway through which value moves between roles under defined conditions. Pipes represent intentional, auditable transitions rather than generic transfers.

---

## External Liquidity Rail

An external liquidity rail is a decentralized market venue used for conversion or access to USDDD. External liquidity rails are not authoritative sources of protocol value or truth.

---

## Protocol Truth

Protocol truth is the state of the DIGDUG.DO system as reconstructed from canonical ledgers, snapshot pricing, and on-chain state. Protocol truth is independent of UI representations or market narratives.

---

## Closing Note

All protocol documentation, interfaces, and communications are expected to conform to the definitions established in this glossary. Where ambiguity arises, this glossary is the final reference.

---

*End of Terminology Glossary.*
