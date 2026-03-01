# 🚀 Overflowing-n8n

This repository is my personal **n8n** workflow library. It centralizes various automations designed to simplify my everyday life, aggregate data, or connect services together. If it's useful for me, it can be useful for someone else.

Each folder contains a specific workflow with its own JSON file and dedicated documentation.

---

## 📂 Workflow Summary

| Folder | Description | Status |
| --- | --- | --- |
| **[Strasbourg Theater](https://www.google.com/search?q=./strasbourg)** | Movie showtimes scraper (Vox, UGC, Cosmos, ...) + AI + Discord. | ✅ Stable |
| *Coming soon...* | *New automations currently in development.* | 🚧 |

---

## 🛠️ General Installation

To use any of these workflows in your n8n instance:

1. **Navigate** to the workflow folder you are interested in.
2. **Copy** the content of the `.json` file.
3. **Paste** it directly into your n8n editor interface.
4. **Configure the Credentials**: Most workflows use third-party APIs (Mistral, Discord, etc.). You will need to link your own accounts in the corresponding nodes.

---

## 🤖 Why use these workflows?

* **Ready to use**: No need to rebuild the logic from scratch.
* **Optimized**: Uses minimal JavaScript code and leverages AI when relevant for formatting.
* **Modular**: Easy to adapt for other cities or other messaging platforms (Telegram, Slack, etc.).

---

## 🔧 Prerequisites

* An **n8n** instance (Cloud or self-hosted).
* The specific credentials mentioned in the README of each folder.