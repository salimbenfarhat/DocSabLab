# Documentation de l'API Shortlinks

## Introduction

Cette API permet de gérer des liens courts (shortlinks) pour diverses URL. Elle expose des routes permettant de créer, lire, mettre à jour et supprimer des shortlinks. Construite avec NestJS, cette API suit le modèle REST et est déployée sur Vercel.

## Base URL

L'API est accessible à l'URL suivante :  
https://sbsb-api.vercel.app/api

## Cas d'utilisation

Prenons l'exemple concret de gestion de deux URLs : l'URL de **Leboncoin** et **Microsoft**.

---

## Routes

### 1. Créer un Shortlink

**URL:** `/shortlinks`  
**Méthode:** `POST`  
**Description:** Crée un nouveau shortlink.  

- Exemple de requête pour ajouter **Leboncoin** et **Microsoft** :

- Requête : `POST /shortlinks`

```json
{
  "url": "https://www.leboncoin.fr",
  "shortUrl": "leboncoin"
}
```

```json
{
  "url": "https://www.microsoft.com",
  "shortUrl": "microsoft"
}
```

- Réponse: Code 201 (Créé) : Retourne l'objet du shortlink créé.

```json
{
  "id": 1638482804500,
  "url": "https://www.leboncoin.fr",
  "shortUrl": "leboncoin"
}
```

### 2. Récupérer tous les Shortlinks

**URL:** `/shortlinks`  
**Méthode:** `GET`  
**Description:** Récupère tous les shortlinks existants.  

- Exemple de requête pour afficher tous les shortlinks :

- Requête : `GET /shortlinks`

- Réponse: Code 200 (OK) : Retourne une liste de shortlinks.

```json
[
  {
    "id": 1638482804500,
    "url": "https://www.leboncoin.fr",
    "shortUrl": "leboncoin"
  },
  {
    "id": 1638482804501,
    "url": "https://www.microsoft.com",
    "shortUrl": "microsoft"
  }
]
```

### 3. Mettre à jour un Shortlink

**URL:** `/shortlinks/:id`  
**Méthode:** `PUT`  
**Description:** Met à jour un shortlink existant.
**Paramètres:** `id: ID` du shortlink à mettre à jour.

- Exemple de requête pour modifier l'URL de **Microsoft** vers **Facebook** :

- Requête : `PUT /shortlinks/1638482804501`

```json
{
  "id": 1638482804501,
  "url": "https://www.microsoft.com",
  "shortUrl": "microsoft"
}
```

- Réponse: Code 200 (OK) : Retourne l'objet du shortlink mis à jour.

```json
{
  "id": 1638482804501,
  "url": "https://www.facebook.com",
  "shortUrl": "facebook"
}
```

### 4. Supprimer un Shortlink

**URL:** `/shortlinks/:id`  
**Méthode:** `DELETE`  
**Description:** Supprime un shortlink existant.  
**Paramètres:** `id: ID` du shortlink à supprimer.

- Exemple de requête pour supprimer l'URL de **Facebook** :

- Requête : `DELETE /shortlinks/1638482804501`
- Réponse: Code 200 (OK) : Retourne l'objet du shortlink supprimé.

```json
{
  "id": 1638482804501,
  "url": "https://www.facebook.com",
  "shortUrl": "facebook"
}
```
