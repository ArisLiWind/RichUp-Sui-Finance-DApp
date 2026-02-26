# RichUp-Sui-Finance-DApp

RichUp is a decentralized personal financial behavior management system built on Sui.

It externalizes self-discipline into verifiable cryptographic proofs:
AI runs locally to guide emotionally sensitive spending,
while the blockchain stores only minimal signed commitments (hash + timestamp).
No fund custody. No private key custody.

---

## Core Modules

- Payment Aggregation Entry (Web2 bridge trigger)
- On-chain Commitment Layer (hash records only)
- Goal & Rule Engine (local-first logic layer)
- On-device AI Intervention System
- Privacy & Encryption Layer
- Smart Contract Proof Layer (PoC)

---

## Tech Stack

- Sui (Move)
- React + TypeScript
- @mysten/sui SDK
- Web Crypto API (SHA-256)
- On-device / private AI model

---

## System Flow

1. User edits rule locally (JSON never uploaded).
2. Frontend computes SHA-256(rule_json).
3. Wallet signs the hash.
4. Transaction calls `register_rule` to store hash on-chain.
5. Chain stores: rule_hash + owner + timestamp.
6. Raw rule and emotional context remain local.

Event flow:
event_json → hash → wallet sign → publish_event

---

## Move Contract Interface (PoC)

register_rule(rule_hash: vector<u8>, expires_at: u64)

publish_event(event_hash: vector<u8>, timestamp: u64)

---

## Security Model

- Only hashes stored on-chain.
- All writes require wallet signature.
- No custody of funds.
- No custody of private keys.
- All transactions publicly auditable.

---

## Repository Structure

richup-sui/
├─ contracts/        # Move proof contract
├─ sdk/              # hash + tx builder
├─ frontend/         # rule editor + wallet interaction
├─ ai/               # on-device model
└─ docs/             # architecture & runbook

---

## License

MIT
