# AtlasEcho

Built for Base

AtlasEcho is a small Base-aligned repository that provides a quick “snapshot + verify” loop for Base networks using official Coinbase tooling. It’s designed for repeated checks of RPC availability, chain identity, and simple read-only balance queries.

## Quick Start Concept

Typical flow:
- Select a Base network (Mainnet or Sepolia)
- Connect a wallet using OnchainKit UI
- Run the snapshot to fetch chainId, latest block, and (optionally) a balance for an entered address
- Cross-check results via Basescan

## Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Project Layout

app/  
- atlasEcho.ts  
  React entry component wiring OnchainKit wallet UX with Base JSON-RPC reads via Viem.

Typical supporting files (recommended):
- package.json
- tsconfig.json
- index.html / main.tsx

## How It Works

Primary file: app/atlasEcho.ts

Runtime behavior:
- Initializes OnchainKitProvider for the selected Base chain
- Uses OnchainKit Wallet for connection UX
- Uses Viem to run Base RPC reads:
  - getChainId
  - getBlockNumber
  - getBalance (native ETH) for a supplied address
- Keeps explorer context visible via Basescan URLs

## Libraries

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client used for Base JSON-RPC reads

## Installation and Running

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies with your preferred package manager and run with a standard React/Vite or Next.js dev server.

## Author

GitHub: https://github.com/embers1algebra

Public contact (email): embers_algebra_0l@icloud.com

X: https://x.com/tawannacowan

## License

MIT License

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0x9F3da84D9285EFdab771C53F29310719A9c913EF 

Deployment and verification:
- https://sepolia.basescan.org/address/0x9F3da84D9285EFdab771C53F29310719A9c913EF   
- https://sepolia.basescan.org/0x9F3da84D9285EFdab771C53F29310719A9c913EF/0#code  

Contract #2 address:  
0xCdA81c2bA3deda31a1FEf5D914e3370A8c1050aC

Deployment and verification:
- https://sepolia.basescan.org/address/0xCdA81c2bA3deda31a1FEf5D914e3370A8c1050aC 
- https://sepolia.basescan.org/0xCdA81c2bA3deda31a1FEf5D914e3370A8c1050aC/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
