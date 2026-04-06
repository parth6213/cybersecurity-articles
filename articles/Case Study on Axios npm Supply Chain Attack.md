# 🚨 Case Study on Axios npm Supply Chain Attack

---

## 🧠 What is a Supply Chain Attack?

A **supply chain attack** is a type of cyberattack where attackers don’t target you directly —
instead, they compromise something you already **trust and depend on**.

👉 This could be:

* A library you import
* A dependency your project uses
* A package from a package manager like npm

---

### 🎯 How it actually works

Instead of breaking into your system…

👉 Attackers insert malicious code into a trusted component
👉 That component gets distributed to thousands (or millions) of developers
👉 And when you install or update it — the attack reaches you

💀 No hacking needed.
You deliver the malware to yourself.

---

### 💡 Simple Analogy

Imagine a food supply chain 🍽️

* You trust a restaurant
* The restaurant trusts a supplier
* If the supplier is compromised…
  👉 everyone eating the food gets affected

👉 In tech:
If a dependency is compromised,
**every application using it becomes vulnerable.**

---

### ⚠️ Why This is So Dangerous

* You trust the source → no suspicion
* The code looks normal → hard to detect
* It spreads automatically → massive scale
* It often runs during install/update → no user action needed

---

### 🚨 In Modern Development

Today, developers don’t write everything from scratch.

👉 A single project may depend on **hundreds of external packages**

Which means:

> **Your application is only as secure as your weakest dependency.**

And that’s exactly what attackers exploit.

---

### 🔥 One-Line Reality

👉 **“In a supply chain attack, trust becomes the vulnerability.”**

---

## 📦 Understanding the Ecosystem

* npm → where developers install packages
* Axios → one of the most trusted HTTP libraries

👉 Millions of downloads
👉 Used in almost every JS project

That trust became the attack vector.

---

## 🎬 The Real Attack Story

This wasn’t random.
This was **planned, staged, and executed with precision.**

---

## 🕒 The Exact Timeline

📅 **March 30, 2026 — 05:57 UTC**
👉 `plain-crypto-js@4.2.0` published (clean version to build trust)

---

📅 **March 30, 2026 — 23:59 UTC**
👉 `plain-crypto-js@4.2.1` published
👉 Malicious payload added via:

```bash
node setup.js
```

---

📅 **March 31, 2026 — 00:05 UTC**
👉 Security scanners flagged it as malware (within minutes)

---

📅 **March 31, 2026 — 00:21 UTC**
👉 Malicious Axios version published:

* axios@1.14.1
  👉 Using compromised maintainer account

---

📅 **March 31, 2026 — 01:00 UTC**
👉 Another version released:

* axios@0.30.4
  👉 Targeting older users (legacy branch)

---

📅 **~03:30 UTC**
👉 npm removed compromised versions
👉 Access tokens revoked

---

## 🧨 What Was the Trick?

👉 A fake dependency: `plain-crypto-js`

* Looked legitimate
* Had a hidden **postinstall script**
* Executed automatically during installation

👉 No clicks. No warnings. No suspicion.

---

## ☠️ Malware Name & Behavior

🧠 **Dropper:** SILKBELL (`setup.js`)
🧠 **RAT:** WAVESHAPER.V2

---

### What it actually did:

* Executed silently during install
* Connected to attacker-controlled server (C2)
* Downloaded second-stage payload
* Enabled remote command execution
* Stole sensitive data (tokens, env variables)
* Cleaned traces after execution

👉 Full remote control was possible.

---

## 🕵️ Who Was Behind This?

👉 Attributed to **North Korea-linked threat actors**

* Google tracks: **UNC1069**
* Microsoft tracks: **Sapphire Sleet**

👉 Known for:

* Supply chain attacks
* Crypto theft
* Advanced cyber operations

---

## ⚠️ Why This Attack Was So Dangerous

* Trusted package (Axios)
* No visible malicious changes
* Auto execution during install
* Cross-platform infection
* Very short attack window

👉 You didn’t get hacked…
**you installed the attack yourself.**

---

## 💥 Real Impact

* Developer machines compromised
* Secrets & API keys leaked
* CI/CD pipelines exposed
* Remote access to systems

👉 In many cases:
**Assume full compromise**

---

## 🛡️ How Can We Prevent This?

The truth is…
You can’t stop updates from coming.
But you **can control what you trust.**

---

### 🔍 1. Don’t Install Blindly

Before installing any package, quickly check:

* GitHub repository
* Maintainer activity
* Sudden version changes

👉 If something feels off, it probably is.

---

### 📦 2. Lock Your Dependencies

Never auto-install latest versions in production.

Use:

```bash
package-lock.json
```

👉 This ensures you install only tested versions.

---

### ⚠️ 3. Be Careful with New Updates

* Sudden new version? → Wait
* Unknown dependency added? → Investigate

👉 Early versions are often the most risky.

---

### 🚨 4. Watch for Postinstall Scripts

Many attacks hide here.

👉 Always check:

* `package.json` → scripts section

If you see something suspicious… don’t install.

---

### 🔐 5. Use Basic Security Checks

Run:

```bash
npm audit
```

👉 It helps detect known vulnerabilities.

---

### 🧠 6. Think Before You Install

Ask yourself:

👉 “Do I really need this package?”
👉 “Is this from a trusted source?”

---

## 💡 Final Reality

You can’t trust every package…
But you can build the habit of verifying before trusting.

👉 **And that habit is what keeps you safe.**


👉 "Trust packages slowly, but verify them quickly."
