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

Il y a un **second workflow** (`strasbourg-webhook.json`), la version **webhook** qui permet d'utiliser ce workflow comme une **API**.

### Fonctionnement

On envoie une requête GET avec un paramètre `days`, ça exécute les nodes qui appellent l'API Allociné puis ça renvoie le JSON clair, nettoyé et mergé par film.

### Endpoint

```
GET https://n8n.wyligr.fr/webhook/api/ttheater?days={N}
```

- `days=0` → Aujourd'hui (par défaut)
- `days=1` → Demain
- `days=7` → Dans 7 jours

### Exemples de requêtes

```bash
# Films d'aujourd'hui
curl "https://n8n.wyligr.fr/webhook/api/ttheater"
# ou
curl "https://n8n.wyligr.fr/webhook/api/ttheater?days=0"

# Films de demain
curl "https://n8n.wyligr.fr/webhook/api/ttheater?days=1"

# Films dans 3 jours
curl "https://n8n.wyligr.fr/webhook/api/ttheater?days=3"

# Avec POST
curl -X POST "https://n8n.wyligr.fr/webhook/api/ttheater" \
  -H "Content-Type: application/json" \
  -d '{"days": 2}'
```

### Réponse

```json
{
  "date": "2026-04-22",
  "dayOffset": 2,
  "displayDate": "mardi 22 avril",
  "liste_films": [
    {
      "titre": "DUNE: DEUXIÈME PARTIE",
      "duree": 166,
      "seances": {
        "UGC": [{"time": "20:30", "isVost": false}],
        "Vox": [{"time": "21:00", "isVost": true}]
      }
    }
  ]
}
```

### Use case

Ce webhook est utilisé par [**Minuit.strs**](https://cinema.wyliam.fr), la version web de ce workflow. Au lieu de recevoir la data sur Discord, tout est réuni sur un seul dashboard web.

> **Note** : L'endpoint utilise `ttheater` (double t) pour éviter les collisions avec la version production.
