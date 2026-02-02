# USDDD MONETARY POLICY  
A Deterministic Fuel and Accounting Framework for DIGDUG.DO

---

## 1. Purpose and Scope

This document defines the monetary policy governing USDDD, the internal fuel and accounting unit of the DIGDUG.DO protocol. It specifies how USDDD is introduced, constrained, accounted for, and released into circulation, and clarifies the economic principles that distinguish USDDD from speculative or yield-bearing instruments.

This policy is intended to be read as a protocol-level constitution. It describes invariant properties, governing mechanisms, and lifecycle semantics that remain valid across software versions, interface changes, and market conditions. Where future protocol phases introduce additional freedoms or mechanisms, those changes will extend this policy explicitly rather than override it implicitly.

---

## 2. Nature of USDDD

USDDD is not a currency in the conventional sense, nor is it a representation of debt, equity, or guaranteed return. It is a protocol fuel and internal accounting unit whose primary purpose is to meter participation, express cost, and anchor deterministic value distribution within DIGDUG.DO.

USDDD exists to ensure that protocol actions have measurable economic weight and that rewards distributed by the protocol can be evaluated against verifiable input costs. Its design explicitly avoids embedding assumptions about external price stability, profit expectations, or market efficiency.

Accordingly, USDDD must be understood as a conserved quantity within a governed system, rather than as an asset whose meaning is derived from market perception.

---

## 3. Supply Philosophy

The monetary philosophy of USDDD is grounded in supply restraint and accounting clarity. The protocol does not treat deposits, activity, or entitlement as automatic justification for circulating supply expansion. Instead, it enforces a separation between economic entitlement and transferable token supply.

This separation is critical. It allows the protocol to account for value owed, accrued, or referenced without prematurely increasing circulating supply. In doing so, it prevents hidden inflation, preserves interpretability of metrics, and ensures that supply changes correspond to explicit participant actions rather than passive system state.

USDDD therefore follows a principle of conditional issuance: supply expands only at defined boundaries, under explicit rules, and with on-chain traceability.

---

## 4. Mint-on-Withdraw Semantics

The primary mechanism enforcing supply discipline is mint-on-withdraw. Under this model, USDDD may be tracked by the protocol as an entitlement or balance in a non-circulating state, while remaining absent from transferable supply until a withdrawal event occurs.

When a participant becomes eligible to withdraw USDDD, the protocol mints the corresponding amount on-chain at the moment of withdrawal. Prior to this event, the entitlement exists only within protocol accounting and does not contribute to circulating supply.

This approach ensures that circulating supply reflects realized exits from the protocol rather than internal bookkeeping. It also guarantees that every minted unit of USDDD corresponds to a deliberate, auditable action by a participant.

Mint-on-withdraw is not an optimization; it is a foundational safeguard against premature or ambiguous issuance.

---

## 5. Lifecycle States

USDDD may exist in multiple lifecycle states defined by protocol rules. These states represent qualitative differences in how USDDD may be used, transferred, or referenced, rather than differences in economic value.

A non-circulating or locked state represents accounted entitlement. A withdrawable state represents eligibility for minting. A circulating state represents freely transferable supply under on-chain rules.

Transitions between these states are governed by explicit protocol conditions and are always traceable through canonical ledgers and on-chain events. At no point does USDDD silently change state without producing verifiable evidence.

---

## 6. Interaction with the Fund Network

The Fund Network is the primary gateway through which USDDD entitlement is introduced into the system. Participants deposit capital under protocol-defined conditions and receive USDDD entitlement subject to lifecycle constraints.

The Fund Network does not guarantee returns, yields, or profits. Instead, it provides a structured mechanism for transforming capital participation into protocol fuel exposure under deterministic rules.

Any accrual references associated with Fund Network participation are informational signals derived from protocol performance metrics. They do not constitute promises, obligations, or enforceable claims beyond what is explicitly defined by protocol rules at the time of withdrawal.

---

## 7. Accrual Reference and Policy Bounds

The protocol computes an accrual reference to express the relationship between value distributed and fuel consumed over time. This reference is derived from canonical accounting and is intentionally bounded within predefined limits.

The accrual reference serves as a descriptive signal, not a prescriptive guarantee. It exists to inform participants about protocol conditions, not to assure outcomes.

By enforcing upper and lower bounds, the protocol prevents short-term volatility or anomalous activity from producing extreme or misleading signals. This bounded approach reflects a conservative monetary posture appropriate for a system operating independently of market price authority.

---

## 8. Snapshot Valuation and Accounting Integrity

USDDD-related distributions and metrics are expressed using snapshot-based valuation. Snapshot pricing anchors value calculations to defined time windows rather than real-time market prices.

This method ensures that historical accounting remains stable and reproducible. It prevents later market movements from retroactively altering the interpretation of past events.

Snapshot valuation is not an attempt to simulate market efficiency. It is an accounting tool designed to preserve consistency, auditability, and temporal fairness.

---

## 9. External Markets and Non-Dependence

USDDD may be exchanged on external decentralized markets for operational convenience. These markets are not treated as authoritative sources of value or truth by the protocol.

The monetary policy of USDDD does not include peg defense, price targeting, or liquidity guarantees. Any alignment between external market prices and internal reference values is incidental rather than enforced.

This non-dependence protects the protocol from thin-liquidity distortions and ensures that internal accounting remains meaningful even when markets are immature or adversarial.

---

## 10. Governance, Upgradability, and Constraints

USDDD is implemented using upgradeable on-chain architecture to allow controlled evolution of the protocol. Upgrades are constrained by administrative roles and are publicly traceable.

Monetary policy changes affecting supply semantics, lifecycle states, or accrual computation are considered protocol-semantic changes. Such changes require explicit documentation updates and on-chain evidence.

Minor software updates, interface changes, or performance optimizations do not alter monetary policy unless they modify the rules defined in this document.

---

## 11. Forward Compatibility

This monetary policy is designed to remain valid across protocol phases. Future phases may introduce additional freedoms, instruments, or mechanisms, but they must do so in a manner consistent with the principles established here.

Where extensions are introduced, they will be layered on top of this policy rather than contradict it. The core commitments to deterministic accounting, explicit issuance, and verifiability are intended to remain invariant.

---

## 12. Closing Statement

USDDD is designed to be boring in the ways that matter and precise in the ways that count. It does not promise profit, predict markets, or rely on narratives. Instead, it enforces clarity: every unit accounted for, every unit minted traceable, every metric reproducible.

In doing so, USDDD serves as a stable internal reference for DIGDUG.DO, allowing the protocol to evolve without losing its economic integrity.

---

*End of Monetary Policy.*
