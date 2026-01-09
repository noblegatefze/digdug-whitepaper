**Relationship to GENESIS.md**

**This document is subordinate to the principles defined in GENESIS.md.  
Where conflicts arise, GENESIS.md takes precedence.**

This document specifies the current monetary policy, issuance mechanics, and lifecycle posture of USDDD within the constraints established at Genesis. It may evolve over time while remaining bound by those constraints.


USDDD MONETARY POLICY

A policy specification governing the issuance, allocation, usage, and withdrawal of USDDD, the protocol-native utility unit of DIGDUG.DO.

Version 0.1
Living document


ABSTRACT

USDDD is the protocol-native utility unit of the DIGDUG.DO ecosystem. It functions as a unit of account, access mechanism, and economic coordination layer rather than as a speculative or yield-bearing asset.

This document describes the monetary posture, issuance model, allocation mechanics, and lifecycle considerations governing USDDD. It is not marketing material. It does not promise value appreciation, scarcity, or returns. Its purpose is to define how USDDD behaves as a protocol resource across time and usage conditions.


1. MONETARY POSTURE

USDDD is a long-term adaptive protocol fuel.

The protocol makes no declaration of fixed supply, hard scarcity, or predetermined deflationary schedules. Any future changes to issuance, allocation limits, or access policies are subject to protocol governance and must remain consistent with the immutable constraints defined in GENESIS.md.

USDDD is intended to be born and sustained through actual participant usage. Value and stability, if they emerge, do so as a consequence of sustained protocol activity rather than discretionary control, guarantees, or pre-seeded trust.

This posture inverts the traditional stablecoin model. USDDD grows through usage first, credibility second, and only later—if ever—through broader settlement roles.


2. USDDD BALANCE TYPES

The protocol recognizes two distinct categories of USDDD balance.

Allocated USDDD is issued programmatically by the protocol under defined allocation rules. It is non-withdrawable and exists solely to enable participation in protocol mechanics.

Acquired USDDD is obtained through explicit settlement (for example, payment in USDT). Acquired USDDD represents user-supplied capital committed to protocol usage and is withdrawable from Genesis onward.

For user experience purposes, both balances are displayed as a unified USDDD balance in the terminal interface. Internally, they are accounted for separately.


3. SPENDING PRIORITY

When USDDD is consumed for protocol interactions, balances are spent in the following order:

First, Allocated USDDD  
Second, Acquired USDDD

This priority ensures that protocol-issued allocations serve their intended purpose before paid capacity is consumed, and prevents accidental depletion of acquired USDDD.


4. ALLOCATION ISSUANCE

USDDD allocation occurs through two primary mechanisms.

Genesis Allocation is a one-time protocol allocation granted upon registration. Its purpose is to bootstrap initial participation.

Daily Allocation is automatically credited on a fixed time interval. Allocation is time-based rather than balance-dependent and requires no manual claim action by the user.


5. ALLOCATION CAPS

Allocated USDDD is subject to a maximum capacity cap.

Once the cap is reached, further automatic allocation is suspended. Allocation resumes only after usage reduces the allocated balance below the cap.

At Genesis launch, the following parameters apply:

Daily Allocation: 5 USDDD  
Base Allocation Cap: 20 USDDD

These values are initial parameters and may be adjusted through protocol policy or governance. They do not represent permanent guarantees.


6. ADAPTIVE CAPACITY

The protocol may increase a participant’s allocation capacity based on lifetime acquired USDDD.

This mechanism is framed strictly as a capacity adjustment rather than a reward, bonus, or yield. Allocation rate does not increase; only the maximum capacity to absorb future allocations may change.

No explicit tiers, thresholds, or entitlements are promised. Exact mechanics remain adjustable and governance-controlled.


7. WITHDRAWALS

Allocated USDDD is never withdrawable.

Acquired USDDD becomes withdrawable from Genesis onward. Withdrawals are initiated by the user and require payment of network gas in the native token of the selected chain.

The protocol does not impose withdrawal fees.


8. FEES AND PROTOCOL REVENUE

DIGDUG.DO earns protocol revenue exclusively through the consumption of USDDD required for protocol interactions.

The protocol does not collect network gas fees and does not impose withdrawal fees at launch.


9. LIFECYCLE CONSIDERATIONS

This monetary policy applies across protocol stages unless explicitly revised.

During Zero Stage, all behavior is simulated and withdrawals are disabled.

From Genesis onward, live contracts are deployed and acquired USDDD becomes withdrawable.

Future stages may introduce policy refinements through governance, provided they remain consistent with Genesis constraints.


10. NON-GOALS AND LIMITATIONS

This policy does not promise value appreciation, yield, or scarcity.

It does not guarantee stability outcomes.

It does not grant discretionary monetary authority to any participant, sponsor, or administrator.

USDDD exists to coordinate access, behavior, and resource allocation within the DIGDUG.DO protocol.


CLOSING NOTES

USDDD is designed to earn trust through usage rather than assertion.

The monetary policy prioritizes survivability, adaptability, and neutrality over speed, hype, or control.

This document may evolve. Its governing principles are intended to endure.
