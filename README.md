# Lunar Bronze (Built for Base)

Lunar Bronze is a read-only inspection workspace built specifically for the Base ecosystem. It is designed to help developers validate network identity, explore public onchain state, and verify results independently through Basescan without performing any state-changing actions.

---

## Functional Overview

The project focuses on transparency and verification. It enables:
- Wallet connection through Coinbase Wallet SDK (EIP-1193)
- Validation of Base chain identifiers (8453 and 84532)
- Retrieval of block metadata and gas metrics
- Balance and transaction count inspection for arbitrary addresses
- Direct cross-referencing of results via Basescan explorers

All interactions are strictly read-only.

---

## Repository Layout

- app/lunar-bronze.ts  
  Browser-based entry script responsible for wallet connection and Base RPC queries.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - ERC20.sol — a Solidity smart contract that implements the ERC-20 token standard
  - based_contract.sol — a base (foundational) contract meant to be inherited by other contracts

- config/base.networks.json  
  Static network definitions including RPC endpoints, explorers, and chainIds.

- docs/architecture.md  
  Design rationale and architectural notes explaining Base alignment and read-only constraints.

- package.json  
  Dependency manifest referencing Coinbase SDKs and Base ecosystem repositories.

- README.md  
  Primary technical documentation.

---

## Supported Base Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

---

## Purpose and Scope

Lunar Bronze exists as a verification surface for Base tooling. It is intended for:
- Pre-production validation
- Read-only monitoring
- Educational inspection of Base network behavior
- Confirming RPC and explorer consistency

No transactions are signed or broadcast.

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract ERC20.sol address:  
0xA5557b50A32058aB1193D096Adb8F186f0d6477d

Deployment and verification:
- https://sepolia.basescan.org/address/0xA5557b50A32058aB1193D096Adb8F186f0d6477d
- https://sepolia.basescan.org/0xA5557b50A32058aB1193D096Adb8F186f0d6477d/0#code  

Contract based_contract.sol address:  
0xa542F68f804408F068939534d0546E3E1C294F87

Deployment and verification:
- https://sepolia.basescan.org/address/0xa542F68f804408F068939534d0546E3E1C294F87
- https://sepolia.basescan.org/0xa542F68f804408F068939534d0546E3E1C294F87/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.

---

## Tooling and Dependencies

The repository integrates open-source tooling from the Base and Coinbase ecosystems:
- Coinbase Wallet SDK for wallet connectivity
- OnchainKit references for Base-aligned primitives
- viem for typed and efficient RPC communication
- Multiple Base and Coinbase GitHub repositories included as dependencies

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## My socials

GitHub: https://github.com/arid-hipster0m 

Email: arid_hipster0m@icloud.com

Public contact(X): https://x.com/kermitiscool50 
