# Lunar Bronze — Architecture Notes

Design rationale and architectural notes explaining Base alignment and read-only constraints.

---

## Base Alignment

Lunar Bronze is designed as a **Base-first** project:

- Supports **Base Mainnet** (chainId `8453`) and **Base Sepolia** (chainId `84532`)
- Uses official public Base RPC endpoints
- Explorer links resolve to BaseScan domains
- All network metadata is centralized in `config/base.networks.json`

No chain IDs, RPC URLs, or explorer links should be hardcoded in application logic.

---

## Read-only Constraints

The project intentionally operates under **read-only constraints**:

Allowed operations:
- Native ETH balance checks
- Contract code presence checks
- Block number and chain metadata reads
- Token metadata reads (symbol / decimals)

Disallowed in the core scope:
- Sending transactions
- Signing messages
- Managing private keys
- Mutating onchain state

This constraint reduces risk, simplifies validation, and keeps behavior deterministic.

---

## Architectural Rationale

### Centralized Configuration
Network definitions live in JSON to:
- Avoid duplication across code
- Make reviews and audits simpler
- Enable safe, explicit changes to infrastructure settings

### Minimal Surface Area
- Fewer dependencies
- Clear separation between configuration, documentation, and logic
- Easy rollback if requirements change

---

## Tradeoffs

**Pros**
- Simple, auditable behavior
- Predictable testnet validation
- Low operational risk

**Cons**
- No transaction execution paths
- Limited coverage of write-side edge cases

These tradeoffs are intentional and align with the current goals of Lunar Bronze.

---

_Last updated: initial scaffold_
