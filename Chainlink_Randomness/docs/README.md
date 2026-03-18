# 🔗 Chainlink VRF v2 Plus – Developer Guide

A complete guide to using **Chainlink VRF v2 Plus** for generating secure, verifiable randomness in smart contracts.

---

## 📌 What is Chainlink VRF?

Chainlink VRF (Verifiable Random Function) is a service that provides **provably fair and tamper-proof randomness** on-chain.

Unlike traditional randomness (which can be manipulated), VRF ensures:

- 🎲 Unpredictability  
- 🔍 Verifiability  
- 🔒 Security against manipulation  

---

## 🚀 What is VRF v2 Plus?

VRF v2 Plus is an improved version of VRF v2 with:

- Flexible payment options (LINK + Native tokens)  
- Better gas efficiency  
- Easier subscription management  
- Enhanced developer experience  

---

## 🤔 Why Use Chainlink VRF?

### ❌ Problem with Randomness in Smart Contracts

Smart contracts are deterministic. That means:

- `block.timestamp` → manipulatable  
- `blockhash` → predictable to miners  

👉 This leads to exploits in games, lotteries, NFTs  

---

### ✅ Solution: Chainlink VRF

- Random number generated off-chain  
- Cryptographic proof provided  
- Verified on-chain before use  

---

## 🧠 Use Cases

- 🎮 Blockchain Games (loot, outcomes)  
- 🎟️ Lotteries & Raffles  
- 🖼️ NFT minting randomness  
- 🎯 Random airdrops  
- 🧪 Fair selection systems  

---

## ⚙️ How It Works (Simple Flow)

1. Contract requests randomness  
2. Chainlink oracle generates random number  
3. Proof is created  
4. Smart contract verifies proof  
5. Random number is returned  

---

## 🛠️ Prerequisites

- Node.js  
- Hardhat / Foundry  
- Solidity basics  
- Wallet with test ETH  
- Chainlink subscription  

---

## 🔧 Installation

```bash
git clone https://github.com/your-username/vrf-v2-plus-guide.git
cd vrf-v2-plus-guide
npm install

🔑 Setup
1. Create Subscription

Go to: https://vrf.chain.link

Create a subscription

Fund it with LINK or native tokens

Add your contract as a consumer

2. Environment Variables

Create a .env file:

SEPOLIA_RPC_URL=your_rpc_url
PRIVATE_KEY=your_wallet_private_key
VRF_SUBSCRIPTION_ID=your_subscription_id
VRF_COORDINATOR=coordinator_address
KEY_HASH=gas_lane_key_hash
CALLBACK_GAS_LIMIT=500000

---

## 📜 Smart Contract Example

<p>
  <img src="assets/carbon.png" width="600"/>
</p>

## 🚀 Deployment (Hardhat Example)

```bash
npx hardhat compile
npx hardhat run scripts/deploy.js --network sepolia

▶️ Usage

Deploy contract

Add contract as consumer in VRF subscription

Call requestRandomNumber()

Wait for Chainlink to fulfill

Read randomNumber

⚠️ Important Notes

Always set enough callback gas limit

Use correct network-specific coordinator

Never rely on pseudo-random values

Ensure contract is added as consumer

🌐 Supported Networks

Sepolia

Ethereum Mainnet

Polygon

Arbitrum

Avalanche

Check official docs for latest support

📈 Best Practices

Use multiple confirmations for security

Handle failed callbacks

Optimize gas usage

Store randomness properly

❗ Common Errors & Fixes

403 GitHub Push Error → You don’t have permission (fork or request access)

Callback failed → Increase gas limit

No random number returned → Contract not added as consumer

Transaction stuck → Check subscription balance

📚 Resources

Chainlink Docs: https://docs.chain.link/

VRF Dashboard: https://vrf.chain.link