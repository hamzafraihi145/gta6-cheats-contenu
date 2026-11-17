# Contenu de l'appli Cheatpad

Ce dépôt contient `content.json` : les codes de triche et les objectifs affichés dans l'appli.
L'appli télécharge ce fichier à chaque ouverture (et quand on tire une liste vers le bas).
**Pas besoin de republier l'appli sur l'App Store pour ajouter des codes.**

## Ajouter un code depuis github.com (ordinateur ou téléphone)

1. Ouvre `content.json`, puis clique sur le crayon ✏️ (« Edit this file »).
2. **Augmente `version` de 1** (par exemple `1` → `2`). Sans ça, l'appli ignore la mise à jour.
3. Ajoute le code dans la liste `cheats` (attention aux virgules entre les blocs) :

```json
{
  "id": "armes-1",
  "name": "Armes",
  "effect": "Donne un lot d'armes",
  "category": "Armes",
  "playstation": ["R1", "R2", "L1", "✕", "←", "↓", "→", "↑"],
  "xbox": ["RB", "RT", "LB", "A", "←", "↓", "→", "↑"],
  "note": "Désactive les trophées"
}
```

4. Clique sur « Commit changes ». Les téléphones reçoivent la mise à jour en quelques minutes.

Champs facultatifs : `"game": "gta5"` pour un code de GTA 5 (sans ce champ, le code est classé GTA 6),
`"phone": "1-999-…"` pour le numéro à composer sur le téléphone du jeu. Pour un code « téléphone uniquement »,
laisser `"playstation": []` et `"xbox": []`.

Symboles des touches : `△ ○ ✕ □` (PS5), `A B X Y` (Xbox), `L1 R1 L2 R2`, `LB RB LT RT`, `← → ↑ ↓`.
`note` est facultatif (mettre `null` s'il n'y en a pas).

## Ajouter un objectif 100 %

Dans `checklist`, ajoute `{ "id": "...", "title": "...", "detail": "..." }` dans les `items` de la bonne catégorie.

## Ajouter une astuce du jour

Dans `tips`, ajoute `{ "id": "t-mon-astuce", "text": "Ton astuce en une ou deux phrases." }`
(ajoute `"game": "gta6"` ou `"gta5"` si l'astuce concerne un jeu précis). Une astuce différente
s'affiche chaque jour dans l'appli, dans le widget et en notification à 18 h.
N'oublie pas d'augmenter `version`.

## Règles importantes

- **Ne jamais modifier un `id` existant** : la progression des joueurs y est liée.
- Chaque `id` doit être unique.
- Si le fichier contient une erreur (virgule oubliée…), l'appli garde l'ancienne version : rien ne casse,
  mais la mise à jour n'arrive pas. Vérifie le fichier sur https://jsonlint.com en cas de doute.
- N'ajoute que des codes vérifiés : l'assistant IA de l'appli les répète tels quels.
