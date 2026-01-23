**Relationship to GENESIS.md**

**This document is subordinate to the principles defined in GENESIS.md.  
Where conflicts arise, GENESIS.md takes precedence.**

This document specifies the canonical on-chain stack used by DIGDUG.DO and USDDD, including deployed contracts, authority boundaries, routing “pipes”, and custody flow primitives. It is intended as an operational and engineering reference. It may evolve over time while remaining bound by the Genesis principles.


ONCHAIN STACK

A reference specification defining the deployed contracts, wallet roles, and routing architecture of USDDD within DIGDUG.DO.

Version 0.1
Living document


ABSTRACT

The DIGDUG.DO ecosystem uses a deliberately simple on-chain architecture: contracts enforce authority and token rules, while EOAs may be used for routing and custody to preserve operational safety and recoverability during early stages.

This document defines the canonical contract stack (USDDD proxy, implementation, ProxyAdmin, AdminManager), the system’s routing addresses (“pipes”), and the authoritative asset flows for Network Funding (USDT → USDDD) and Terminal Acquire. It is not marketing material. It does not introduce yield language, investment framing, or guarantees. Its purpose is to prevent ambiguity and ensure that custody and authority are consistently understood across engineering, operations, and governance.


1. SCOPE AND INTENT

This document is the canonical reference for:

- what is a contract vs what is an EOA,
- which addresses are authoritative and why,
- how USDT and USDDD are routed through pipes,
- and how custody is structured (hot vs cold) without hard-coding long-term custody decisions.

This document does not define monetary policy, issuance posture, or lifecycle goals. Those are defined in USDDD_MONETARY_POLICY.md and GENESIS.md.


2. CONTRACTS: CANONICAL USDDD STACK

USDDD is deployed using an upgradeable proxy pattern. The public-facing token address remains stable while the logic may be upgraded under explicit authority control.

2.1 USDDD PROXY (PUBLIC TOKEN ADDRESS)

Address:
0x03f65216F340bAC39c8d1911288B1c7CA071e9c3

Function:
- The canonical token address indexed by wallets and explorers.
- Holds USDDD balances (token ledger).
- Emits transfer, mint, and burn events.

Notes:
- All user and system interactions target the proxy address.
- The proxy delegates execution to the current implementation.

2.2 USDDD IMPLEMENTATION (LOGIC / RULES ENGINE)

Address:
0xA6e47a2Bc4D7371660124b56Fc1A042da41E6c12

Function:
- Contains the executable token logic, including mint rule enforcement, permission checks, and token behavior.
- Defines how privileged actions (mint/pause/config) are validated.

Notes:
- Holds no balances.
- Is not interacted with directly by end users.

2.3 PROXYADMIN (UPGRADE AUTHORITY)

Address:
0x035Fe89fB7cB7610a756F2D7fe5154Fca5B2Ed90

Function:
- Controls upgrades by changing which implementation the proxy points to.

Limitations:
- Does not mint.
- Does not hold balances.
- Does not move tokens.

Notes:
- Upgrade authority is intentionally isolated from economic authority.

2.4 ADMINMANAGER (AUTHORITY CONTROLLER)

Address:
0x4ef2b77620EC6BDdA714be2Cbe4dF0D57c7bB16A

Function:
- Controls which entities are authorized to execute privileged actions on the USDDD token (for example: minting and pause control).
- Acts as the canonical permission boundary between human operators and token-level authority.

Notes:
- This contract defines “who is allowed” to perform privileged actions.
- It does not custody tokens as a treasury.


3. WALLETS: AUTHORITY AND ROUTING

EOAs are used for two distinct purposes:

- authority signing (human-controlled),
- routing (“pipes”) and custody (operational flow control).

3.1 AUTHORITY WALLETS (HUMAN-CONTROLLED)

Owner / Deployer (Highest Authority):
0x0A3AF77Fa1bb5682797668bdAcE0E94F7041c72E

Manager (Senior Authority):
0x9A1f50E93bF14538456664e83306f35f769C12B7

Function:
- Sign protocol-critical operations as required by governance and operational policy.
- These wallets are not intended to be general-purpose custody vaults.

3.2 PIPES (ROUTING ADDRESSES)

A “pipe” is a stable routing address that receives assets first, then routes to hot or cold custody according to operational policy. Pipes exist to prevent upstream flows from depending on long-term custody structure.

USDT FUND NETWORK PIPE:
0x55ea686DD14C78985FE1348F040FA68579dd1250

USDDD TREASURY PIPE (MINT RECEIVER):
0x8304C9E29DDB3887E0ee5e1cB81b1AAb6B49B910

Notes:
- Pipes are public by design.
- Pipes are not defined as final custody.
- Hot/cold custody may change over time without changing the pipe addresses.


4. CUSTODY MODEL (HOT VS COLD)

Custody wallets are downstream of pipes and may evolve over time.

Hot custody:
- Minimal operational balances.
- Used only when necessary for execution.

Cold custody:
- Long-term reserves.
- Hardware / multisig / ledger-controlled.
- Multiple cold wallets are explicitly supported.

Custody policy is operational and may change without rewriting protocol history.


5. NETWORK FUNDING FLOW (USDT → USDDD)

Network Funding is an inbound USDT flow that results in USDDD issuance under protocol custody.

Authoritative flow:

Funder USDT
→ Per-position Deposit EOA (system-generated)
→ Sweep (off-chain signer)
→ USDT Fund Network Pipe
→ Hot / Cold custody (operational)
→ USDDD mint (on-chain)
→ USDDD Treasury Pipe
→ Custody buckets (operational)

Key properties:
- Deposit EOAs are unique per position and recoverable.
- Sweeping is an off-chain signing action, not a smart contract.
- USDDD is minted to custody (via pipe), not directly to users.
- User balances remain custodied allocations until protocol unlock conditions permit withdrawal.


6. TERMINAL ACQUIRE FLOW (USDT)

Terminal Acquire follows the same routing discipline.

Authoritative flow:

User USDT
→ Protocol acquire flow
→ USDT routing (pipe)
→ Hot / Cold custody (operational)

Notes:
- USDDD classification (Allocated vs Acquired vs other custody states) is governed by USDDD_MONETARY_POLICY.md.
- The on-chain stack defined here is focused on routing and custody boundaries rather than UX presentation.


7. SPONSORS (ZERO PHASE POSTURE)

During Zero / Pre-Genesis:
- sponsors may supply tokens using EOAs,
- distribution is executed according to protocol rules,
- withdrawals occur according to eligibility constraints.

Sponsor contracts may be introduced later as an additive evolution. This document does not require sponsor contracts as a prerequisite for Zero stage operation.


8. NON-GOALS AND LIMITATIONS

This architecture does not attempt to:
- eliminate EOAs entirely in early stages,
- force custody into contracts prematurely,
- or optimize for maximal on-chain enforcement at the expense of recoverability.

The priority at this stage is:
- clarity,
- safety,
- and non-stranding of funds.


CLOSING NOTES

The on-chain stack is intentionally conservative.

Contracts enforce authority and rule boundaries.  
EOAs provide routing and recoverable custody where appropriate.  
Pipes prevent upstream flows from hard-coding custody decisions.

This document may evolve. The Genesis principles are intended to endure.
