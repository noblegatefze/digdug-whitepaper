# DIGDUG.DO  
A Deterministic Protocol for Verifiable Value Distribution  
and Fuel-Governed Network Participation

---

## Abstract

DIGDUG.DO is a protocol designed to distribute value through verifiable participation while remaining robust under conditions of thin liquidity, immature price discovery, and adversarial external markets. The system introduces a separation between protocol truth and market expression by anchoring all internal accounting to canonical ledgers, snapshot-based valuation, and on-chain state, rather than transient exchange prices.

At the core of the protocol is USDDD, a fuel and accounting unit whose lifecycle is governed by deterministic rules, mint-on-withdraw semantics, and protocol-defined states. DIGDUG.DO further distinguishes between execution surfaces and verification surfaces, allowing the protocol to evolve without compromising auditability or economic coherence.

This paper describes the architecture, lifecycle model, accounting methodology, and phase-based evolution of the DIGDUG.DO protocol as it exists today.

---

## 1. Motivation and Design Philosophy

Early-stage protocols often collapse under their own narratives. In the absence of deep liquidity and mature markets, price becomes noisy, manipulable, and frequently misleading. Yet many systems implicitly treat price as truth, using it to justify rewards, measure performance, or signal legitimacy. This coupling introduces fragility at precisely the moment when a protocol should be most resilient.

DIGDUG.DO is designed from the opposite premise: that protocol truth must remain coherent even when markets are thin, distorted, or temporarily unavailable. Rather than asking “what is the price,” the protocol asks “what occurred,” “what was earned,” and “what is provable.”

The guiding principle of DIGDUG.DO is therefore simple:  
**If an independent observer can reconstruct the protocol’s state from canonical records, then the protocol remains truthful regardless of external conditions.**

This principle informs every major design decision in the system, from fuel issuance to reward accounting to the separation of execution and verification.

---

## 2. Canonical Truth and Deterministic Accounting

DIGDUG.DO defines a strict hierarchy of truth. At the highest level are canonical protocol events: actions executed by users, sponsors, or operators that consume fuel, trigger distributions, or alter state. These events are written into append-only ledgers that serve as the authoritative record of activity.

From these events emerge canonical claims, which represent value owed or distributed by the protocol. Claims are not inferred from UI behavior or wallet balances; they are explicit records tied to protocol rules and timestamps.

To express value in a common unit, the protocol employs snapshot-based valuation. Rather than relying on real-time exchange prices, DIGDUG.DO records time-indexed reference prices and applies them deterministically to claims based on when the underlying event occurred. This ensures that historical accounting remains stable and reproducible.

Finally, all supply, balances, and administrative actions are anchored to on-chain state. Smart contracts do not merely enforce rules; they provide the final, public substrate upon which protocol truth rests.

Together, canonical events, claims, snapshots, and on-chain state form a closed accounting loop. Any observer with access to these sources can independently verify distribution, efficiency, and supply behavior without trusting off-chain assertions.

---

## 3. Architectural Separation: Terminal and Scan

A defining characteristic of DIGDUG.DO is the explicit separation between *doing* and *verifying*.

The **Terminal** is the execution surface of the protocol. It is where actions occur. Users dig, sponsors fund activity, fuel is spent, and claims are initiated. The Terminal enforces participation rules, rate limits, cooldowns, and eligibility constraints. It produces protocol events, but it does not define truth. Its role is to submit structured, validated intent into the system.

The **Scan** is the verification surface. It does not execute actions, accept input, or mutate state. Instead, it observes. Scan reads canonical ledgers, on-chain state, and snapshot tables to reconstruct the protocol’s reality. All public metrics—value distributed, fuel utilized, reward efficiency, accrual references—are derived from Scan’s deterministic view of the system.

This separation is intentional. By decoupling execution from verification, DIGDUG.DO ensures that changes to user interfaces, interaction flows, or operational tooling do not alter protocol truth. The Terminal may evolve rapidly; Scan must remain stable, conservative, and reproducible.

In this sense, Scan functions as the protocol’s public memory, while the Terminal functions as its hands.

---

## 4. USDDD: Fuel, Not Narrative

USDDD is the internal fuel and accounting unit of DIGDUG.DO. It is not designed as a speculative instrument, nor as a promise of profit. Its purpose is to meter participation, express protocol constraints, and provide a common unit for internal measurement.

USDDD enters the system through protocol-defined mechanisms, most notably the Fund Network. However, issuance is deliberately constrained. The protocol distinguishes between entitlement and circulation, allowing USDDD to exist in non-circulating states that are fully accounted for but not yet minted as transferable supply.

This design culminates in mint-on-withdraw semantics. Supply expansion occurs only when a participant explicitly withdraws USDDD from the protocol into a freely transferable state. Until that moment, the protocol tracks entitlement without inflating circulating supply. This approach preserves accounting integrity and prevents premature or hidden inflation.

USDDD therefore functions less like a currency and more like a conserved quantity within a closed system, expanding only at well-defined boundaries.

---

## 5. Snapshot-Based Valuation

A central challenge in value distribution systems is assigning fair and consistent value across time. DIGDUG.DO addresses this through snapshot-based valuation.

When a claim is generated, it is associated with a timestamp. The protocol applies a reference USD price drawn from a snapshot table corresponding to that time window. The value of the claim is therefore fixed at creation, independent of subsequent market movements.

This approach yields several benefits. Historical distributions remain comparable. Short-term price manipulation does not retroactively alter protocol performance. Metrics derived from claims remain stable and interpretable.

Importantly, snapshot pricing does not attempt to predict or control markets. It merely provides a deterministic reference that allows the protocol to speak coherently about value.

---

## 6. Reward Efficiency and Accrual Reference

From canonical fuel spend and snapshot-priced distributions, DIGDUG.DO derives higher-order signals. One such signal is reward efficiency, defined as the ratio between value distributed and fuel consumed over a given window.

This metric is not a marketing number. It is a structural indicator of how effectively the protocol converts participation into distribution. Because both numerator and denominator are canonical, the metric remains meaningful even under volatile external conditions.

The protocol further derives an accrual reference from these signals. This reference is bounded by explicit floors and caps and scaled conservatively. It is not a guarantee, yield, or promise. Rather, it is a protocol-level signal that informs system posture and participant expectations.

By clamping the reference within predefined bounds, the protocol avoids overreacting to short-term fluctuations while still reflecting long-term trends.

---

## 7. External Markets as Utility, Not Authority

USDDD may be exchanged on external decentralized venues to facilitate access, conversion, and operational convenience. These venues are treated as utility rails.

DIGDUG.DO does not treat external market prices as authoritative because early liquidity is often thin, easily manipulated, and slow to reflect internal reality. Accordingly, no peg defense is promised, and no market price is elevated to protocol truth.

Arbitrage may occur. Divergence may occur. The protocol remains indifferent, because its accounting does not depend on external narratives.

This stance is not adversarial to markets; it is defensive of protocol integrity.

---

## 8. Phases, Genesis State, and Version Semantics

DIGDUG.DO evolves through explicit protocol phases. These phases describe economic and governance posture, not software maturity.

The protocol currently operates in **Zero Phase**, during which all core mechanics are live and verifiable, but certain freedoms remain intentionally constrained. Future phases will be declared explicitly and are treated as formal lifecycle transitions.

Separately, the on-chain system includes a **Genesis State** capability flag. This flag enables foundational mechanics required for operations such as initial liquidity. Genesis State has been activated on-chain via a canonical transaction, but this activation does not itself constitute a phase transition.

This distinction is critical: a contract-level capability does not imply a protocol-level declaration.

Versioning reflects this philosophy. The leading digit of the protocol version encodes the phase, while subsequent digits encode major, minor, and hotfix iterations. Terminal and Scan may advance independently in implementation, but their outputs must remain consistent with the same underlying protocol truth.

---

## 9. Wallet Roles and On-Chain Structure

The protocol employs multiple wallets and contracts, each assigned a clear functional role. These include treasury custody, fund network operations, liquidity operations, and administrative control.

To preserve document longevity and avoid drift, this paper defines roles rather than addresses. Canonical addresses are publicly discoverable and verifiable via the Scan surface, ensuring transparency without embedding mutable details into protocol literature.

---

## 10. Security and Verifiability

DIGDUG.DO is designed to be audited by construction. Fuel spend is recorded. Claims are explicit. Supply changes are traceable. Administrative actions occur on-chain.

The primary risks to the system—spam, manipulation, misinterpretation—are mitigated not by secrecy, but by determinism and public verification. If something occurs, it can be proven. If value is distributed, it can be reconstructed.

---

## 11. Conclusion

DIGDUG.DO is not a narrative-driven system. It is an accounting-driven protocol that remains coherent under uncertainty. By separating execution from verification, market expression from protocol truth, and entitlement from circulation, the protocol establishes a foundation capable of scaling without losing interpretability.

In an ecosystem where perception often outruns reality, DIGDUG.DO chooses the opposite path: to make reality so explicit that perception becomes irrelevant.

---

*End of Whitepaper.*
