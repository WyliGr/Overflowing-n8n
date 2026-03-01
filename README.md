# Overflowing-n8n

This repository is my personal **n8n** workflow library. It centralizes various automations designed to simplify my everyday life, aggregate data, or connect services together. If it's useful for me, it can be useful for someone else.

Each folder contains a specific workflow with its own JSON file and dedicated documentation.

---

## 📂 Workflow Summary

| Folder | Description | Status |
| --- | --- | --- |
| **[Strasbourg Theater](https://www.google.com/search?q=./strasbourg)** | Movie showtimes scraper (Vox, UGC, Cosmos, ...) + AI + Discord. | ✅ Stable |
| *Coming soon...* | *Some automations are currently in development.* | 🚧 |

---

## 🛠️ General Installation

To use any of these workflows in your n8n instance:

1. **Navigate** to the workflow folder you are interested in.
2. **Copy** the content of the `.json` file.
3. **Paste** it directly into your n8n editor interface.
4. **Configure the Credentials**: Most workflows use third-party APIs (Mistral, Discord, etc.). You will need to link your own accounts and webhooks in the corresponding nodes.

---

## ❓ Why use these workflows?

Good question! Honestly, use them at your own risk, brother. I'm no automation AI Expert—I'm just playing with n8n features to build stuff that seems cool (and sometimes useful). 

I decided to share these because I think they might help someone else out, which is exactly why this repo is released under the **GLWTPL** (Good Luck With That Public License). I can't promise my shit is perfectly stable, and I am absolutely not responsible for any damages these workflows might cause. 

Play around, tweak them, and good luck!

---

## 🔧 Prerequisites

* An **n8n** instance (Cloud or self-hosted).
* The specific credentials mentioned in the README of each folder.