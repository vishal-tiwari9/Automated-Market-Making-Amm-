# 🦄 Simple AMM (Automated Market Maker)

A minimal **AMM (like Uniswap v2)** built from scratch using **Solidity + Foundry**.
This project demonstrates the core concepts behind decentralized exchanges:

* Liquidity pools
* Constant product formula `x * y = k`
* Adding/removing liquidity
* Swapping tokens without order books

---

## 📂 Project Structure

```
SimpleAMM/
├─ src/
│   ├─ TestToken.sol     # Simple ERC20 test tokens
│   ├─ SimpleAMM.sol     # Core AMM contract
│
├─ script/
│   └─ Deploy.s.sol      # Deployment script
│
├─ test/
│   └─ SimpleAMM.t.sol   # Unit & integration tests
│
├─ lib/                  # External dependencies (OpenZeppelin, forge-std)
└─ foundry.toml          # Project config
```

---

## ⚡ How it Works

1. **Liquidity Providers (LPs)** deposit equal value of Token A and Token B.

   * They receive LP shares.
   * First LP sets the initial ratio.

2. **Swaps** use the constant product formula:

   ```
   x * y = k
   ```

   * If Token A is added, Token B is removed.
   * Price adjusts dynamically (slippage).

3. **Removing Liquidity** lets LPs burn shares to withdraw tokens.

---

## 🛠️ Setup & Installation

1. Install Foundry:

   ```bash
   curl -L https://foundry.paradigm.xyz | bash
   foundryup
   ```

2. Clone this repo:

   ```bash
   git clone <repo-url> && cd SimpleAMM
   ```

3. Install dependencies:

   ```bash
   forge install OpenZeppelin/openzeppelin-contracts
   ```

4. Build:

   ```bash
   forge build
   ```

---

## 🚀 Deployment

To deploy locally (Anvil) or on a testnet:

```bash
forge script script/Deploy.s.sol --fork-url <RPC_URL> --broadcast
```

This deploys:

* **Token A (TKA)**
* **Token B (TKB)**
* **SimpleAMM contract**

---

## ✅ Testing

Run all tests:

```bash
forge test -vv
```

Example tests include:

* Adding liquidity
* Swapping tokens
* Removing liquidity

---

## 📖 Next Steps / Improvements

* Add swap fees (e.g. 0.3% to LPs)
* Implement `swapBForA`
* Add slippage protection
* Deploy to Sepolia / Polygon testnet
* Build a frontend with React + ethers.js

---

## 📜 License

MIT
