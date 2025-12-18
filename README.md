# Base Horizon (Built for Base)

Deployed on Base Mainnet.

Base Horizon is a browser-first reference repository that demonstrates how to connect to the Base ecosystem using Coinbase Wallet SDK and perform structured, read-only inspection of onchain state. The project is intentionally non-destructive and suitable for validating Base tooling and account abstraction–compatible environments.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application explicitly targets Base networks and relies on official Base RPC endpoints.

---

## What the script does

The app.base-horizon.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Base RPC queries:
   - latest block number  
   - ETH balance of the connected address  
4) Generates a concise block summary (timestamp and gas usage)  
5) Allows ETH balance checks for arbitrary addresses  
6) Outputs Basescan links for verification  

No transactions are sent. All interactions are strictly read-only.

---

## Repository structure

- app.base-horizon.ts  
  Browser-based script that connects to a wallet, toggles Base networks, and inspects onchain state.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - storage.sol — contract demonstrating on-chain data storage, constructors, access control via visibility, and custom error handling  
  - array.sol — example contract showcasing dynamic array manipulation, data appending, resetting state, and filtering timestamped records linked to senders  

- package.json  
  Dependency manifest including Coinbase SDKs and multiple repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Base accounts.

- viem  
  RPC client used for Base reads and block inspection.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Base RPC data displayed  
- Block summary available on demand  

---

## License

MIT License

Copyright (c) 2025 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/anorak-rums  
Email: anorak.rums-0t@icloud.com  
Public contact: https://x.com/reecarter5  

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract "storage" address:  
0xf3c7d43ec609381653c4d5a8534090b37aeedd76

Deployment and verification:
- https://sepolia.basescan.org/address/0xf3c7d43ec609381653c4d5a8534090b37aeedd76
- https://sepolia.basescan.org/0xf3c7d43ec609381653c4d5a8534090b37aeedd76/0#code  

Contract "array" address:  
0x5f8e1bf5bbc6c113601212e15bcd13e204df22a9

Deployment and verification:
- https://sepolia.basescan.org/address/0x5f8e1bf5bbc6c113601212e15bcd13e204df22a9
- https://sepolia.basescan.org/0x5f8e1bf5bbc6c113601212e15bcd13e204df22a9/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
