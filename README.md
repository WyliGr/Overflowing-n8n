# 🚀 Overflowing-n8n

Bienvenue dans ma bibliothèque personnelle de workflows **n8n**. Ce dépôt centralise différents automates conçus pour simplifier le quotidien, agréger des données ou connecter des services entre eux.

Chaque dossier contient un workflow spécifique avec son propre fichier JSON et sa documentation dédiée.

---

## 📂 Sommaire des Workflows

| Dossier | Description | Statut |
| --- | --- | --- |
| **[Strasbourg Theater](https://www.google.com/search?q=./strasbourg)** | Scraper de scéances de cinémas (Vox, UGC, Cosmos) + IA + Discord. | ✅ Stable |
| *À venir...* | *Nouveaux automates en cours de développement.* | 🚧 |

---

## 🛠️ Installation Générale

Pour utiliser l'un de ces workflows dans votre instance n8n :

1. **Naviguez** dans le dossier du workflow qui vous intéresse.
2. **Copiez** le contenu du fichier `.json`.
3. **Collez** directement dans l'interface de votre éditeur n8n.
4. **Configurez les Credentials** : La plupart des workflows utilisent des API tierces (Mistral, Discord, etc.). Vous devrez lier vos propres comptes dans les nœuds correspondants.

---

## 🤖 Pourquoi utiliser ces workflows ?

* **Prêts à l'emploi** : Pas besoin de reconstruire la logique de zéro.
* **Optimisés** : Utilisation de code JavaScript minimal et d'IA quand c'est pertinent pour le formatage.
* **Modulaires** : Faciles à adapter pour d'autres villes ou d'autres plateformes de messagerie (Telegram, Slack, etc.).

---

## 🔧 Prérequis

* Une instance **n8n** (Cloud ou auto-hébergée).
* Les credentials spécifiques mentionnés dans le README de chaque dossier.