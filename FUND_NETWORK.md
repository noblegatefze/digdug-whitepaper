# **FUND_NETWORK.md**

User Instructions for Position Creation in the DIGDUG.DO Fund Network

---

## **Purpose**

This document defines the process by which a participant creates a Fund Network position within **digdug.do**.

It is procedural. It does not describe marketing, opinion, or future speculation.
It describes how the system is used.

---

## **Definition of USDDD**

$USDDD is the protocol unit used within DIGDUG.DO.

* It is maintained at a **1:1 reference to USD**
* It functions as **protocol fuel and accounting unit**
* It is issued deterministically through Fund Network participation

At this stage, $USDDD is constrained within protocol mechanics.

---

## **Definition of the Fund Network**

The Fund Network is the mechanism through which:

* External capital (USDT) enters the protocol
* $USDDD is minted
* Yield accrues over time based on protocol rules

It operates under deterministic execution and observable state.

---

## **Preconditions**

Before creating a position, the participant must:

1. Be a registered user of **digdug.do**
2. Have access to their Terminal session
3. Be able to send USDT (BEP-20)

No position can exist without a valid session linkage.

---

## **Procedure: Creating a Fund Position**

### **Step 1 — Register Terminal Account**

Access **digdug.do** and create a user account.

Credentials must be retained by the participant.
The protocol does not recover them.

---

### **Step 2 — Open Fund Interface**

In a separate browser session:

```
https://usddd.digdug.do/fund
```

---

### **Step 3 — Retrieve Session ID**

Within the Terminal:

* Refresh the session
* Locate the **Session ID**
* Copy the value exactly

---

### **Step 4 — Link Session**

Within the Fund interface:

* Input the Session ID
* Confirm linkage

A position cannot be created without a valid linked session.

---

### **Step 5 — Generate Deposit Address**

Request a new deposit address.

This address is:

* Unique per position
* Used as the anchor for minting and accounting

---

### **Step 6 — Submit Capital**

Send USDT to the generated address.

**Constraints:**

* Minimum: 150 USDT
* Maximum: 250,000 USDT

After sending:

* Provide the transaction hash (TXID)
* Await confirmation

---

### **Step 7 — Position Activation**

Upon confirmation:

* The position becomes active
* $USDDD is minted to the deposit address
* Accrual begins

All values are recorded in canonical protocol state.

---

### **Step 8 — Withdrawal**

When withdrawal becomes available:

* The participant may withdraw:

  * Minted $USDDD
  * Accrued $USDDD

Withdrawal is executed to a designated wallet.

---

## **Behavioral Notes**

* All actions are **final once confirmed**
* The protocol does not reverse transactions
* All accounting is deterministic and observable

---

## **Future State**

Upon Mainnet activation (target: Q2 2026):

$USDDD is expected to be interoperable with:

* USDT
* USDC
* ETH
* BTC

This is contingent on external exchange integration.

---

## **Frequently Asked Questions**

### **Is $USDDD a stable unit?**

It is designed to maintain a **1:1 USD reference**.

---

### **What generates yield?**

Yield is produced through **protocol-level mechanics**, not discretionary distribution.

---

### **When can withdrawal occur?**

When the protocol enables withdrawal for the position.

---

### **Is the system live?**

* Protocol: Active (Zero Phase)
* Economic expansion: Pending Mainnet

---

### **What happens below minimum deposit?**

The position may not activate.

---

### **Can multiple positions be created?**

Yes. Each position is independent.

---

## **Support**

For operational issues:

```
usddd@digdug.do
```
