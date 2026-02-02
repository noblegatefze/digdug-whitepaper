# ON-CHAIN ARCHITECTURE  
Deterministic Contract Design and Verifiable State for DIGDUG.DO

---

## 1. Purpose of the On-Chain Layer

The on-chain layer of DIGDUG.DO exists to provide finality, traceability, and public verifiability for protocol-critical state. While much of the protocol’s logic is expressed through canonical ledgers and deterministic accounting off-chain, all authoritative supply, custody, and administrative actions are ultimately anchored on-chain.

The on-chain system is therefore not a convenience layer, nor merely a settlement mechanism. It is the protocol’s immutable substrate, responsible for ensuring that critical transitions—such as issuance, withdrawal, custody movement, and administrative control—are observable, auditable, and irreversible once executed.

DIGDUG.DO deliberately avoids overloading the blockchain with transient or high-frequency events. Instead, it reserves on-chain execution for events whose correctness must not depend on trust in operators, interfaces, or off-chain computation.

---

## 2. Design Principles

The on-chain architecture of DIGDUG.DO is guided by four primary principles: determinism, minimalism, separation of concerns, and upgrade discipline.

Determinism ensures that on-chain actions have unambiguous effects and can be independently verified without contextual interpretation. Minimalism limits on-chain logic to what must be enforced by consensus, leaving derived metrics and aggregation to verifiable off-chain systems. Separation of concerns isolates custody, issuance, administration, and observation into distinct components. Upgrade discipline allows evolution without sacrificing historical integrity.

These principles collectively reduce attack surface while preserving long-term adaptability.

---

## 3. Contract Roles and Boundaries

The DIGDUG.DO on-chain system is composed of multiple contracts and wallets, each assigned a narrowly defined role. These roles are architectural abstractions rather than specific implementations, allowing the system to evolve without breaking conceptual guarantees.

At the center is the **USDDD token contract**, which represents the protocol fuel in its transferable form. This contract enforces fixed decimal precision, balance accounting, and transfer rules consistent with the protocol’s monetary policy.

Issuance authority is constrained. The token contract does not mint freely in response to deposits or internal accounting. Instead, minting is gated by explicit protocol actions, most notably withdrawal events that satisfy mint-on-withdraw semantics.

Custody is handled through designated treasury roles. Treasury contracts or wallets hold protocol-owned assets and serve as sinks and sources for controlled movements. They do not autonomously issue or destroy supply; they act under explicit protocol authority.

Operational flow is handled through **pipes**—conceptual pathways that move value between roles under predefined conditions. Pipes are not generic routers; they represent deliberate, auditable transitions such as fund intake, entitlement tracking, or withdrawal settlement.

Administrative authority is separated into dedicated roles responsible for upgrades, configuration changes, and emergency actions. These roles are intentionally visible and constrained, ensuring that any exercise of authority leaves an on-chain trace.

---

## 4. Upgradeability and Proxy Architecture

DIGDUG.DO employs upgradeable contract patterns to balance immutability with long-term viability. Upgradeability is not used to bypass protocol commitments but to allow correction, extension, and refinement under explicit governance control.

Proxy-based architectures separate storage from logic. This ensures that historical balances, state variables, and accounting records persist across upgrades, while allowing implementation code to evolve.

Crucially, upgrade authority is treated as a first-class risk surface. Administrative roles capable of executing upgrades are isolated, observable, and limited. The existence of upgradeability is disclosed by design, not hidden, and its exercise is intended to be exceptional rather than routine.

An upgrade does not retroactively alter past state. It changes the rules going forward, leaving historical behavior intact and auditable.

---

## 5. Mint-on-Withdraw at the Chain Level

Mint-on-withdraw semantics are enforced at the boundary between protocol accounting and on-chain supply. The on-chain layer is responsible for ensuring that circulating USDDD supply increases only when a withdrawal event is executed.

Prior to withdrawal, entitlement may exist entirely off-chain, represented by canonical ledgers and protocol state. The blockchain remains unaware of this entitlement until the protocol explicitly requests minting.

When a withdrawal is executed, the on-chain system mints the corresponding amount of USDDD and transfers it to the designated recipient. This minting event is public, final, and traceable.

This architecture ensures that on-chain supply is a reflection of realized exits rather than internal promises. It also guarantees that total circulating supply can always be reconciled against observable mint events.

---

## 6. Relationship Between On-Chain State and Scan

Scan functions as an observer of the on-chain system. It does not control contracts, submit transactions, or mutate state. Instead, it reconstructs protocol reality by reading on-chain events, balances, and administrative actions, and combining them with canonical off-chain ledgers.

This observer model is intentional. By keeping Scan read-only with respect to on-chain state, the protocol prevents feedback loops where analytics could influence execution.

On-chain state is therefore primary, but not sufficient on its own to describe protocol behavior. It gains meaning through deterministic interpretation, which Scan provides transparently.

---

## 7. Genesis State as a Capability Flag

The on-chain system includes a Genesis State capability flag that enables certain foundational mechanics required for protocol operation. This flag exists to gate functionality, not to signal economic phase transitions.

Activation of Genesis State is an on-chain event that can be independently verified. Its activation allows specific actions—such as initial liquidity operations—to occur. It does not, by itself, declare a change in protocol phase.

This separation prevents semantic overload and ensures that lifecycle declarations remain deliberate, documented, and explicit.

---

## 8. External Market Interaction

On-chain contracts may interact with external decentralized exchanges or liquidity venues to facilitate conversion and operational flows. These interactions are strictly utilitarian.

The on-chain system does not enforce price targets, pegs, or stabilization mechanisms. Any price relationship between USDDD and external assets emerges organically from market activity rather than protocol enforcement.

By avoiding embedded market assumptions, the on-chain layer remains robust even under adverse or irrational trading conditions.

---

## 9. Security Posture

Security in DIGDUG.DO is achieved through structural clarity rather than complexity. Each contract has a narrow mandate. Each administrative action is observable. Each supply change is explicit.

Attack surfaces are reduced by limiting on-chain logic to essential functions and by avoiding implicit coupling between off-chain computation and on-chain execution.

The protocol assumes that all on-chain actions will be scrutinized. Accordingly, it is designed so that scrutiny strengthens rather than weakens confidence.

---

## 10. Forward Evolution

The on-chain architecture of DIGDUG.DO is intended to evolve alongside the protocol’s lifecycle phases. Future phases may introduce additional contracts, refined roles, or expanded capabilities.

Such evolution will occur through explicit upgrades, documented changes, and observable on-chain events. The core commitments—to deterministic supply control, explicit authority, and verifiability—are intended to remain invariant.

---

## 11. Closing Remarks

The on-chain system of DIGDUG.DO is not a replica of the protocol; it is its anchor. By restricting the blockchain to what must be enforced by consensus and exposing everything else to transparent verification, the protocol achieves a balance between rigor and flexibility.

In doing so, DIGDUG.DO treats the blockchain not as a canvas for narratives, but as a ledger for truth.

---

*End of On-Chain Architecture.*
