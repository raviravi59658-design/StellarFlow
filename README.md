# 🌊 StellarFlow  
### When Money Learns to Move Like Information


**A Beginner-to-Builder Guide to Stellar Payments**

---

## 🚀 Project Overview

This repository supports an educational project that explains **why global money movement is slower than messages**, and how the **Stellar Network** enables **fast, low-cost, borderless payments** — effectively making **money move like information**.

The project includes:

* A **60-second educational video**
* A **comprehensive technical guide**
* Example Stellar code demonstrating key concepts
* Explanations of accounts, assets, DEX functionality, and path payments
* A foundation for builders to start building on Stellar

This content was submitted as an entry for **Ideatón Fin de Año – Track 2: Educational Content**, powered by *Tellus Cooperative* & *Stellar Chile*.

---

## 📹 Video (Explainer)

Watch the 60-second video that introduces the core idea:

▶️ [https://youtube.com/shorts/t0jv0wY46rE?feature=share](https://youtube.com/shorts/t0jv0wY46rE?feature=share)

The video answers the question:

> **Why does a text message travel the world in seconds, but money takes days?**

---
## 🌐 Project Submission on X

The full project, including the video and links, was submitted and shared on **X (formerly Twitter)**:  

🐦 [View Submission on X](https://x.com/raviravi660665/status/2005336086550282500)

This post provides a quick summary of the project and links to all resources for easy reference.

---

## 📖 Full Technical Guide

Read the complete *Beginner to Builder* guide on Medium:

📝 [https://medium.com/@raviravi59658/when-money-learns-to-move-like-information-a-beginner-to-builder-guide-to-stellar-payments-9bb8a31da826](https://medium.com/@raviravi59658/when-money-learns-to-move-like-information-a-beginner-to-builder-guide-to-stellar-payments-9bb8a31da826)

This guide builds a layered understanding of Stellar:

1. Introductory intuition (money vs information)
2. Why modern finance has friction
3. How Stellar works (accounts, assets, transactions, validators)
4. Path payments and liquidity routing
5. Anchors and compliance
6. Real world use cases
7. Code examples for developers

---

## 📌 What This Project Teaches

This project helps you understand:

### ✅ The Problem

* Why traditional cross-border payments are slow and opaque
* Why financial infrastructure is still less efficient than information networks

### ✅ The Solution

* Stellar as a **payment-focused blockchain network**
* Fast settlement in seconds
* Predictable, tiny fees
* Real financial use cases (remittances, stablecoins, global payments)

### ✅ How Stellar Works (High Level)

* Accounts and public/private keys
* Network assets (XLM, USDC, custom tokens)
* Validators and consensus
* Built-in decentralized exchange
* Path payments and routing

---

## 💡 Example Code (Starter Templates)

Below are snippet examples you’ll find in this repo (also shown in the article):

### Create & Fund a Testnet Account

```javascript
import StellarSdk from "@stellar/stellar-sdk";
import fetch from "node-fetch";

const pair = StellarSdk.Keypair.random();
console.log("Public Key:", pair.publicKey());
console.log("Secret Key:", pair.secret());

await fetch(
  `https://friendbot.stellar.org?addr=${encodeURIComponent(pair.publicKey())}`
);
console.log("Account funded on Testnet");
```

### Simple Payment Transaction

```javascript
import StellarSdk from "@stellar/stellar-sdk";

const server = new StellarSdk.Server("https://horizon-testnet.stellar.org");
const source = StellarSdk.Keypair.fromSecret("SECRET");
const account = await server.loadAccount(source.publicKey());

const tx = new StellarSdk.TransactionBuilder(account, {
  fee: StellarSdk.BASE_FEE,
  networkPassphrase: StellarSdk.Networks.TESTNET,
})
  .addOperation(
    StellarSdk.Operation.payment({
      destination: "DESTINATION",
      asset: StellarSdk.Asset.native(),
      amount: "5",
    })
  )
  .setTimeout(30)
  .build();

tx.sign(source);
await server.submitTransaction(tx);
```

---

## 🎯 Who This Is For

* Beginners curious about blockchain and payments
* Developers exploring Stellar and Soroban
* Students learning financial infrastructure
* Builders looking for real examples
* Educators and content creators focused on Web3 adoption

---

## 📚 Resources

* 🛠️ **Freighter Wallet** – [https://www.freighter.app](https://www.freighter.app)
* ⚙️ **Stellar Laboratory** – [https://laboratory.stellar.org](https://laboratory.stellar.org)
* 📄 **Stellar SDK Docs** – [https://developers.stellar.org/docs/sdks](https://developers.stellar.org/docs/sdks)
* 🧠 **Official Soroban Docs** – [https://developers.stellar.org/docs/smart-contracts](https://developers.stellar.org/docs/smart-contracts)

---

## 🏆 Submission Context

This educational project was submitted for:

**Ideatón Fin de Año – Track 2: Educational Content**
Organized by: **Tellus Cooperative & Stellar Chile**

Submission included:
✔ Article link
✔ Video link
✔ Educational approach

---

## 🚀 Contributing

If you want to:

* add more examples
* improve technical clarity
* expand to other languages
* build apps on Stellar

feel free to open an issue or submit a pull request.

---

## 📄 License

This project is licensed under **MIT License** — free to learn from, share, and build upon.


