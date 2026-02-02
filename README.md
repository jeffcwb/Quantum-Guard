# 🔐 QuantumGuard - Quantum Entropy Wallet Generator

[![Live Demo](https://img.shields.io/badge/demo-live-success.svg)](https://securewallet-1igs.onrender.com)
[![License](https://img.shields.io/badge/license-proprietary-red.svg)](LICENSE)
[![Security](https://img.shields.io/badge/security-audited-success.svg)](#-security)
[![Python](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![Solana](https://img.shields.io/badge/blockchain-Solana-blueviolet.svg)](https://solana.com/)

**Generate cryptocurrency wallet seeds using real quantum entropy from vacuum fluctuations, combined with client-side cryptographic randomness.**

🔗 **Try it now:** [https://securewallet-1igs.onrender.com](https://securewallet-1igs.onrender.com)

---

## ✨ What Makes QuantumGuard Different

Most crypto wallets rely on pseudo-random number generators (PRNGs) — mathematical algorithms that, while complex, are theoretically predictable given enough computational power. **QuantumGuard eliminates this attack vector entirely.**

### Our Approach

```
🌌 Quantum Entropy (Server)
      │
      ├── ANU Quantum Labs → Vacuum Fluctuation → 32 bytes
      │
      ▼
💻 Local Entropy (Your Browser)
      │
      ├── Web Crypto API → Hardware CSPRNG → 32 bytes
      │
      ▼
🔐 XOR Mixing (Client-Side)
      │
      └── BIP-39 Derivation → 12-Word Seed Phrase
```

**Key principle:** Even if one entropy source is compromised, the other keeps your seed secure.

---

## 🚀 Features

| Feature | Description |
|---------|-------------|
| 🌌 **Quantum Entropy** | Real measurements from ANU's quantum vacuum fluctuation detector |
| 🔒 **Client-Side Only** | Your seed phrase is generated in your browser — never sent to servers |
| ⛓️ **Blockchain Payment** | Fair pay-per-generation model (0.05 SOL via Solana) |
| 🛡️ **Anti-Replay Protection** | Each payment can only generate one wallet |
| 🔐 **Transparent Security** | Built-in audit tools to verify our claims |
| 📊 **Honest Metrics** | Shannon entropy calculation on actual data |
| ⚡ **Fast & Reliable** | Sub-second generation with automatic fallback |

---

## 🎯 How It Works

### User Journey

1. **Visit the interface** at [securewallet-1igs.onrender.com](https://securewallet-1igs.onrender.com)
2. **Send exactly 0.05 SOL** to our payment address (Solana mainnet)
3. **Paste transaction hash** from your wallet confirmation
4. **Receive quantum entropy** mixed with local randomness
5. **Get your 12-word seed phrase** — save it offline immediately
6. **Auto-destruct in 5 minutes** — we don't store anything

### Security Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      YOUR BROWSER                            │
│                                                              │
│  • Connects to payment wallet (Phantom/Solflare)            │
│  • Generates local entropy (crypto.getRandomValues)         │
│  • Mixes server + local entropy via XOR                     │
│  • Derives BIP-39 mnemonic locally (Ethers.js)              │
│  • Displays seed phrase to you ONLY                         │
│                                                              │
└─────────────────────────────────────────────────────────────┘
                            ▲
                            │ HTTPS (entropy only, never seed)
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    QUANTUMGUARD SERVER                       │
│                                                              │
│  • Validates payment on Solana blockchain                   │
│  • Fetches quantum entropy from ANU Labs                    │
│  • Returns 32 bytes of randomness                           │
│  • Stores transaction hash (prevent reuse)                  │
│  • NEVER sees your final seed phrase                        │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛡️ Security Guarantees

### What We Do

✅ **Validate real payments** — Blockchain RPC verification (not just signature format)  
✅ **Prevent replay attacks** — Database constraint on transaction hashes  
✅ **Rate limiting** — 10 attempts per minute per IP  
✅ **Restrict CORS** — Only our domain can call the API  
✅ **Zero-knowledge architecture** — Server never receives your seed phrase  
✅ **Honest source reporting** — If quantum source fails, we tell you (fallback to CSPRNG)  
✅ **Auto-destruct timer** — Seed phrase removed from browser memory after 5 minutes  

### What We Don't Do

❌ Store seed phrases (not even encrypted)  
❌ Log sensitive data  
❌ Require email or personal information  
❌ Use proprietary "black box" entropy  
❌ Charge subscription fees  

### Audit Yourself

Click **"Auditoria Client-Side"** in the interface to verify:
- HTTPS connection
- Domain authenticity
- No suspicious iframes
- Browser CSPRNG availability
- Whitelisted scripts only
- Backend operational status

---

## 💳 Pricing

**0.05 SOL per wallet generation**

- No subscriptions
- No hidden fees
- One-time payment per seed phrase
- Payment verified on Solana mainnet
- Instant generation after confirmation

**Why we charge:** Running quantum entropy services (ANU API), blockchain validation, and secure infrastructure costs money. Pay-per-use ensures sustainability without ads or data harvesting.

---

## 🔬 Technology Stack

- **Quantum Entropy:** [ANU Quantum Random Number Generator](https://qrng.anu.edu.au/) (vacuum fluctuation measurements)
- **Blockchain:** Solana mainnet (payment verification)
- **Client Library:** Ethers.js (BIP-39 derivation)
- **Crypto Standard:** BIP-39 (12-word mnemonic)
- **Frontend:** Vanilla JS + Tailwind CSS
- **Backend:** Python + FastAPI
- **Database:** Supabase (PostgreSQL)

---

## 📱 Supported Wallets

Any Solana wallet works for payment:
- Phantom
- Solflare
- Backpack
- Sollet
- Ledger (via Solana app)

---

## ❓ FAQ

### Is this really quantum randomness?

Yes. We fetch entropy from the Australian National University's quantum random number generator, which measures vacuum fluctuations — a fundamentally unpredictable quantum process. When ANU is unavailable, we fall back to your browser's CSPRNG and clearly indicate this.

### Why not just use my browser's randomness?

You could, but combining two independent sources (quantum + local) provides defense-in-depth. Even if one source is somehow compromised, the other protects you.

### Do you store my seed phrase?

**Absolutely not.** The seed derivation happens entirely in your browser using Ethers.js. We only send you the raw entropy — you mix it locally and derive the mnemonic. We never see the final result.

### Can I use the same transaction twice?

No. Each transaction hash is stored in our database with a unique constraint. This prevents someone from intercepting your hash and generating multiple wallets from one payment.

### What if I lose my seed phrase?

We cannot recover it. This is a feature, not a bug. **Write it down on paper immediately** and store it in a safe place. Consider metal backups for fire/water resistance.

### Is the code open source?

The frontend code is visible in your browser (right-click → View Source). The backend is proprietary to prevent clones, but the architecture is documented here. You can audit the client-side logic yourself.

### What happens if your service shuts down?

Your seed phrases are generated **in your browser** and stored **by you offline**. Even if QuantumGuard disappears tomorrow, your wallets remain accessible with your saved seed phrases.

---

## 📞 Contact & Support

- 🌐 **Website:** [securewallet-1igs.onrender.com](https://securewallet-1igs.onrender.com)
- 📧 **Email:** quantumguard@outlook.com
- 🐦 **Twitter:** [@QuantumGuardLabs](https://twitter.com/)
- 💬 **Issues:** For feature requests or bug reports (security issues via email only)

---

## ⚠️ Disclaimer

This software generates cryptographic material for cryptocurrency wallets. **You are solely responsible for:**

- Securely storing your seed phrase (offline, on paper/metal)
- Verifying all transactions before confirming
- Understanding the risks of cryptocurrency
- Maintaining multiple backups in different locations
- Never sharing your seed phrase with anyone

**QuantumGuard Labs:**
- Does NOT store your seed phrases
- Does NOT have access to your wallets
- CANNOT recover lost seed phrases
- CANNOT reverse or refund payments after generation

**Use at your own risk.** Cryptocurrency involves risk of total loss.

---

## 📜 License

Copyright © 2026 QuantumGuard Labs. All rights reserved.

The frontend code visible in your browser is provided for transparency and audit purposes. Unauthorized copying, modification, or redistribution of any component of this system is prohibited.

For licensing inquiries, contact: quantumguard@outlook.com

---

## 🙏 Acknowledgments

- **Australian National University** — Quantum RNG infrastructure
- **Solana Foundation** — Blockchain payment rails  
- **Ethers.js Team** — BIP-39 implementation
- **Web Crypto API** — Browser-native cryptographic primitives

---

**Built with 🔐 by QuantumGuard Labs**

*Eliminating PRNG predictability, one wallet at a time.*
