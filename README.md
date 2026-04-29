#  PactPool — Commitment Capital

> DECRYPTO Hackathon — Problem Statement 3: DeFi

Savings with real skin in the game — enforced by code.

Lock ETH with a goal. Break your pact early and pay a penalty. That penalty gets redistributed proportionally to savers who stayed disciplined. No bank. No middleman. No exceptions.

---

##  Links

- Live Demo: https://YOUR_USERNAME.github.io/pactpool-decrypto
- Contract:(Sepolia): `PASTE_CONTRACT_ADDRESS_HERE`
- Etherscan: https://sepolia.etherscan.io/address/PASTE_CONTRACT_ADDRESS_HERE

---

##  The Core Idea

Most savings apps fail because there's no real cost to quitting. PactPool flips this with **Commitment Capital** — your ETH is locked by a smart contract, and breaking the pact funds the rewards of everyone who didn't.

> Break early → pay up to 30% penalty → that ETH flows into a shared pool → disciplined savers claim it as a bonus on withdrawal.

---

##  Features

###  Commitment Tiers
Choose your risk-reward level before locking:

| Tier | Penalty Range | Pool Share Multiplier |
|------|--------------|----------------------|
|  Bronze | 10–15% | 1.0× |
|  Silver | 15–22% | 1.5× |
|  Gold | 20–30% | 2.5× |

Higher tier = higher penalty if you break, but a larger slice of the penalty pool if you complete.

### Goal Categories
Tag your savings goal with a category for the public Goal Wall:

 Travel ·  Study ·  Safety ·  Health ·  Gadget ·  Business

###  Penalty Curve Simulator
Interactive canvas chart that lets you visualize exactly how much you'd lose vs. keep at any point in your lock period — before you commit. Adjust lock period, ETH amount, and withdrawal day in real time.

###  Live Countdown Timer
Once locked, your active pact card shows a live days/hours/minutes/seconds countdown to your unlock date, along with a real-time penalty percentage if you were to withdraw at that exact moment.

###  Live Activity Ticker
A scrolling marquee strip shows real on-chain events — new pacts locked, early withdrawals with penalty amounts, and completed claims with bonus rewards.

###  Goal Wall (dashboard.html)
A public, no-wallet-needed board showing every saver's goal, category, progress bar, and status. Filter by Active / Completed / Pact Broken. Search by goal text or wallet address.

###  Auto Wallet Reconnect
If MetaMask was previously connected, the app reconnects automatically on page load — no extra click needed.

---

##  How It Works

1. Pick a tier (Bronze / Silver / Gold) and select a goal category
2. Write your goal, enter ETH amount, and set a lock period (1–90 days)
3. Preview your pact — see unlock time, max/min penalty, and pool share multiplier before confirming
4. Lock ETH — MetaMask signs the transaction; your pact is live on Sepolia
5. Your goal appears on the public Goal Wall immediately
6. Two outcomes:
   -  Reach unlock date → withdraw full ETH + claim your share of the penalty pool
   -  Withdraw early → pay 10–30% dynamic penalty, which is redistributed to other savers

---

##  Tech Stack

| Layer | Tech |
|---|---|
| Smart Contract | Solidity 0.8.20, Sepolia testnet |
| Frontend | Pure HTML + Vanilla JS — zero npm, zero build step |
| Web3 Library | Ethers.js 5.7.2 (CDN) |
| Wallet | MetaMask (auto-reconnect supported) |
| Fonts | Bricolage Grotesque + IBM Plex Mono |
| Charts | Native HTML5 Canvas (no library) |
| Hosting | GitHub Pages |

---

##  Project Structure

```
pactpool-decrypto/
├── index.html        # Main app — deposit, pact card, simulator, ticker
├── dashboard.html    # Goal Wall — public saver board with filter + search
└── README.md
```

---

##  Contract Functions Used

| Function | Description |
|---|---|
| `deposit(lockDays, goal)` | Payable — locks ETH with goal string |
| `withdraw()` | Withdraw with or without penalty depending on timing |
| `getPoolStats()` | Returns total ETH locked, penalty pool, total savers |
| `getSaverInfo(address)` | Returns amount, unlock time, goal, penalty now, progress % |
| `getAllSavers()` | Returns array of all saver addresses (used by Goal Wall) |

---

##  Security

- Reentrancy protected — Checks-Effects-Interactions pattern; amount zeroed before transfer
- Basis points math — Penalty calculated using 10,000 = 100% to prevent integer truncation errors
- No admin keys — Fully permissionless contract; no owner can pause, drain, or modify it
- Compiler — Solidity 0.8.20 with built-in overflow protection

---

##  Run Locally

No setup required. Just open `index.html` in Chrome with MetaMask installed and switched to **Sepolia testnet**. The page works in demo mode before the contract address is set.

---

##  Pitch in One Line

> "An FD you can't break without funding someone else's dream."

---

##  Team

- Vaibhav — Smart Contract Dev (Solidity, Remix, Etherscan verification)
- Sai Samarth — Frontend Dev (Deposit UI, wallet connect)
- Yatin arora — Frontend Dev (Goal Wall / Dashboard)
- Harsh Vardhan — Integration Lead (ABI wiring, GitHub Pages deployment, demo prep)

---

Built in 2 hours at DECRYPTO Hackathon · Problem Statement 3: DeFi
