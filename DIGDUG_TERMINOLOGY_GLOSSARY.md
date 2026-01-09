**Relationship to GENESIS.md**

**This glossary is subordinate to the principles defined in GENESIS.md.  
Where conflicts arise, GENESIS.md takes precedence.**

This document defines the canonical terminology used throughout the DIGDUG.DO protocol, including documentation, terminal interfaces, and governance texts.


DIGDUG.DO TERMINOLOGY GLOSSARY

A reference document defining the normative language of the DIGDUG.DO protocol.

Version 0.1
Living document


ABSTRACT

DIGDUG.DO is a text-first, protocol-driven system. Terminology is therefore not cosmetic.  
Words define expectations, constraints, and mental models.

This glossary exists to prevent semantic drift, preserve regulatory clarity, and ensure that all participants—users, sponsors, developers, and future contributors—operate with a shared understanding of protocol concepts.

Where ambiguity arises, definitions in this document take precedence.


1. PROHIBITED TERMINOLOGY

The following terms must not be used as protocol primitives or system-level language:

- giveaway  
- free  
- bonus  
- prize  
- earn (when referring to USDDD issuance)  
- reward (when referring to USDDD issuance)  

These terms may appear only in external marketing or explanatory contexts. They must not appear in protocol logic, accounting, or terminal system messages.


2. CORE PROTOCOL TERMS

USDDD  
The protocol-native utility unit of DIGDUG.DO. USDDD functions as a unit of account, access mechanism, and coordination resource. It is not introduced as a speculative or yield-bearing asset.

Allocated USDDD  
Protocol-issued USDDD credited under defined allocation rules. Allocated USDDD is non-withdrawable and exists solely to enable participation in protocol mechanics.

Acquired USDDD  
USDDD obtained through explicit settlement (e.g. payment in USDT). Acquired USDDD represents user-supplied capital committed to protocol usage and is withdrawable from Genesis onward.

Allocation  
Rule-based issuance of USDDD by the protocol.

Genesis Allocation  
A one-time protocol allocation granted upon registration.

Daily Allocation  
An automatically credited periodic allocation subject to cooldown and capacity limits.


3. INTERACTION TERMS

Dig  
A USDDD-paid interaction with a Treasure Box.

Claim  
A recorded entitlement to a reward token, stored in the protocol ledger.

Withdraw  
A user-initiated on-chain action to receive claimed tokens.


4. DISTRIBUTION CONSTRUCTS

Treasure Box  
A rule-defined container governing token distribution.

Sponsored Treasure Box  
A Treasure Box deployed, funded, and configured by a sponsor.

Protocol Incentive Box  
A Treasure Box created and operated by DIGDUG.DO for protocol-level incentives and early engagement.

Reward Pool  
The on-chain token balance backing a Treasure Box.

Treasure Contract  
A smart contract holding reward pools and enforcing distribution logic.  
Sponsor boxes use dedicated contracts. Protocol incentive boxes may use shared contracts per chain.


5. PARTICIPANT ROLES

User  
An individual interacting with the protocol through the terminal interface.

Sponsor  
An entity that deploys and funds Sponsored Treasure Boxes.

Protocol (DIGDUG.DO)  
The system governing rules, issuance, coordination, and enforcement.


6. ACCOUNTING TERMS

Ledger  
The internal accounting system tracking claims, reservations, and withdrawals.

On-chain Balance  
The actual token balance observed on the blockchain.

Available Balance  
On-chain balance minus reserved (claimed but unwithdrawn) tokens.


7. DESIGN INTENT

This glossary is intentionally restrictive.

Its purpose is not to constrain expression, but to ensure that protocol language remains precise, neutral, and durable across market cycles and governance changes.

Terminology may evolve, but semantic discipline is a core design requirement of DIGDUG.DO.
