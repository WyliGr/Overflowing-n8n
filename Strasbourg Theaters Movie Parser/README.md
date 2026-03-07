# 🥨 Strasbourg Theater Movies Parser

Ce workflow **n8n** récupère quotidiennement les séances des cinémas strasbourgeois via l'API Allociné, les traite via une IA (Mistral) et publie un condensé élégant sur **Discord**.

## 📍 Cinémas Inclus

Le workflow est pré-configuré pour les salles suivantes :

* **UGC Ciné Cité Rivétoile** (P0963)
* **Le Cosmos** (P0026)
* **Cinéma Vox** (P0600)
* **Star** (P0027)
* **Star Saint-Exupéry** (P0025)

## ⚙️ Fonctionnement

1. **Extraction** : Récupération des données JSON brutes pour chaque cinéma.
2. **Traitement** : Nettoyage des données en JavaScript pour ne garder que l'essentiel (Titres, Durées, Horaires).
3. **Intelligence Artificielle** : Utilisation d'un agent **Mistral AI** pour reformater le texte de manière humaine et esthétique.
4. **Notification** : Envoi du message final sur un salon Discord dédié.

## 🚀 Installation

1. **Import** : Copiez le contenu de `strasbourg.json` et collez-le dans votre instance n8n.
2. **Credentials** :
* Configurez vos identifiants **Mistral Cloud** dans le nœud *Mistral Cloud Chat Model*.
* Connectez votre **Discord Bot** dans le nœud *Send a message*.


3. **Personnalisation** (Optionnel) :
* Par défaut, le message est envoyé chaque matin à **7h00**. Modifiez le nœud *Schedule Trigger* pour changer l'heure.
* L'ID du salon Discord est déjà renseigné mais a modifier à votre convenance, assurez-vous que votre bot a les permissions d'écriture sur votre serveur.


## 📝 Exemple de rendu Discord

> **DUNE: DEUXIÈME PARTIE** (2h46)<br>
> • **Vox** : 14:00 (VO)| 20:30<br>
> • **UGC** : 13:30 | 17:00 (VOSTFR)| 21:00<br>
> • **Le Cosmos** : 18:15<br>

## Webhook
Il y a un *second workflow*, la version **webhook** qui permet d'utiliser ce workflow comme une *API*. On envoie une *requête GET*, ça execute mes nodes qui call l'API de Allociné puis ça renvoie le JSON clair, nettoyé et merge par film.

Ce webhook a un usecase qui peut être important dans un projet comme [**Minuit.strs**](https://cinema.wyliam.fr) qui est la version web de ce Workflow. Au lieu de recevoir la data sur discord, tout est réuni sur un seul même dashboard web.