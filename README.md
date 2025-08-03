# EcoMorph
A savings vault that lets users earn simulated yield and vote on real-world environmental projects. Built for the Morph testnet.
# EcoMorph 🌱

A savings vault that lets users earn simulated yield and vote on real-world environmental projects. Built for the Morph Holesky testnet.

---

## 🧠 Overview

This protocol redirects simulated yield from stablecoin deposits to verified environmental projects — without touching user principal. Users vote each cycle to decide where the yield goes. No middlemen. No token hype. Just on-chain execution.

---

## 🧩 How It Works

- Users deposit testnet stablecoin (MockUSDT) into the vault and receive eMVT share tokens 1:1.
- eMVT represents both voting power and redeemable principal.
- Simulated yield (5% APR) accrues over time and can be redirected to projects.
- Users vote once per 7-day cycle. The winning project receives the full yield for that round.
- Principal can be withdrawn at any time — it’s never donated.

---

## 🧱 Smart Contracts (Morph Holesky)

| Contract           | Address |
|--------------------|---------|
| MockUSDT.sol       | `0xd3c34744b7724231069a853cB232a4CdA237e0d7` |
| YieldVault.sol     | `0x4faE15dC71C0354b50ff10C996Bc0A1e34d22a70` |
| CommunityFund.sol  | `0x5ECe6108fcAf0717F581Ea7CDA8551769ec06D5f` |
| Ballot.sol         | `0x29677dEe0AfC3bbfAA7aeFe7430b984029025382` |

---

## ⚙️ Installation & Setup (Remix + Static Frontend)

### 1. Deploy Smart Contracts

Use Remix with MetaMask on Morph Holesky Testnet. Deploy in order:

- `MockUSDT.sol` → no params  
- `YieldVault.sol` → params: MockUSDT address, `6`  
- `CommunityFund.sol` → param: YieldVault address  
- `Ballot.sol` → no params  

Save the deployed addresses.

---

### 2. Set Up Frontend

```bash
git clone https://github.com/EcoMorphProject/EcoMorph.git
```
Update tokens.js:
export const MOCK_USDT_ADDRESS   = "0x...";
export const YIELD_VAULT_ADDRESS = "0x...";
export const RPC = "https://rpc-quicknode-holesky.morphl2.io";
export const CHAIN_ID = 2810;

3. Test the Flow
Connect MetaMask (Morph Holesky)

Use mint() in MockUSDT.sol to get test tokens

Deposit → Simulate yield → Vote → Harvest → Release funds

Withdraw anytime

🛣️ Roadmap & Next Steps
Phase 1 – MVP (Now)

MockUSDT vault, eMVT shares, vote logic, yield simulation

Fully functional testnet dApp (deployed + working)

Phase 2 – Real Yield

Integrate ERC-4626 vaults with actual yield (e.g. Aave)

Automate harvests using cron or Chainlink Keepers

Phase 3 – Mainnet

Move to L2 with real stablecoins

Optional: On-chain governance for project selection

🔗 Links & Resources
🌐 Live site: https://myecosteps.com

🧪 DoraHacks BUIDL: https://dorahacks.io/buidl/30401

🎥 Demo video: [coming soon]

🧾 Snapshot space: https://snapshot.org/#/your-space.eth
cd EcoMorph
python -m http.server 8080  # or any static server
