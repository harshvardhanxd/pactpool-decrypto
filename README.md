# ⬡ PactPool — Save with Skin in the Game

> DECRYPTO Hackathon · Problem Statement 3: DeFi · Sepolia Testnet

## 🎯 What is PactPool?

PactPool is a **commitment savings protocol** on Ethereum. Lock ETH with a savings goal and a time period. Break your pact early? You pay a dynamic penalty (10–30%) that gets redistributed to the savers who stayed disciplined. Everyone's goal is publicly visible on the Goal Wall — accountability built in.

**Inspired by:** Stickk.com + PoolTogether + the science of commitment devices.

---

## 🚀 Live Demo

🌐 **Frontend:** [your-github-username.github.io/pactpool-decrypto](https://your-github-username.github.io/pactpool-decrypto)

📄 **Contract on Sepolia Etherscan:** [View Contract](https://sepolia.etherscan.io/address/PASTE_CONTRACT_ADDRESS_HERE)

---

## ⚙️ How It Works

1. **Deposit ETH** with a goal (e.g., "Buy a MacBook") and lock period (1–365 days)
2. Your goal appears on the public **Goal Wall**
3. **Complete on time** → Withdraw your ETH + proportional share of the penalty pool (profit from others' failures!)
4. **Withdraw early** → Pay 10–30% dynamic penalty (more time remaining = bigger penalty). Penalty goes to the pool.

### Penalty Formula
```
penalty = principal × (BASE_10% + (timeRemaining/totalDuration × 20%))
```
Minimum penalty: 10% · Maximum penalty: 30% · Uses basis points math (no rounding errors)

---

## 🔧 Tech Stack

| Layer | Technology |
|-------|-----------|
| Smart Contract | Solidity 0.8.20 |
| Testnet | Sepolia (Ethereum) |
| Frontend | HTML + Vanilla JS |
| Wallet | MetaMask via Ethers.js 5.7 |
| Deployment | GitHub Pages |
| Contract IDE | Remix IDE |

---

## 📁 Project Structure

```
pactpool-decrypto/
├── index.html       # Main page: wallet connect + deposit form
├── dashboard.html   # Goal Wall: all savers, filter, search
├── PactPool.sol     # Solidity smart contract (also verified on Etherscan)
└── README.md
```

---

## 🏗️ Local Setup

No build step needed — pure HTML.

```bash
git clone https://github.com/YOUR_USERNAME/pactpool-decrypto
cd pactpool-decrypto
# Open index.html in browser, or:
npx serve .
```

---

## 📜 Contract Details

- **Network:** Sepolia Testnet
- **Address:** `PASTE_CONTRACT_ADDRESS_HERE`
- **Verified:** Yes (Etherscan)
- **Key Functions:**
  - `deposit(lockDays, goal)` — payable, locks ETH
  - `withdraw()` — handles both early (penalty) and on-time (bonus) withdrawals
  - `getAllSavers()` — returns all depositor addresses (for Goal Wall)
  - `getSaverInfo(address)` — full saver details including live penalty calculation
  - `getPoolStats()` — total locked, penalty pool, saver count

---

## 👥 Team

| Member | Role |
|--------|------|
| [Name 1] | Smart Contract (Solidity) |
| [Name 2] | Frontend — Deposit UI |
| [Name 3] | Frontend — Goal Wall |
| [Name 4] | Integration & Deployment |

---

## 🎤 Pitch Summary

> **Problem:** Savings apps fail because there's nothing stopping you from withdrawing early. No accountability, no incentive to stay committed.

> **Solution:** PactPool makes your savings *public* and makes breaking your commitment *costly* — your penalty funds bonuses for the disciplined savers. Gamified, transparent, automatic.

> **Innovation:** Dynamic penalty redistribution using basis-points math. Every withdrawal — early or on-time — is handled by an immutable smart contract. No middleman. No cheating.

---

*Built at DECRYPTO Hackathon in 2 hours by a team of 4.*
