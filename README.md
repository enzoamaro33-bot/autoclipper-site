# Site AUTOCLIPPER (site/)

Site statique (aucune dépendance, aucun build) : page d'accueil + Terms of
Service + Privacy Policy. Prévu pour servir de site officiel public lors de
la validation TikTok Developer, hébergé gratuitement sur GitHub Pages.

Ce dossier est totalement indépendant de l'application Node/Express
(`app/webapp/`) : aucun fichier partagé, aucune dépendance commune.

## Lancer en local

Aucune installation nécessaire. Depuis la racine du projet :

```bash
cd site
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000 dans un navigateur.

(N'importe quel serveur de fichiers statiques fonctionne — `npx serve`,
l'extension "Live Server" de VS Code, etc. Tous les liens internes sont en
chemins relatifs, donc le site fonctionne aussi ouvert directement en
double-cliquant sur `index.html`, sans serveur.)

## Déploiement sur GitHub Pages

Deux options, au choix selon comment le dépôt Git est organisé :

**Option A — dossier `/site` sur la branche `main`**
1. Repo GitHub → Settings → Pages
2. Source : "Deploy from a branch"
3. Branch : `main`, dossier : `/site`
4. Enregistrer — GitHub publie `https://<utilisateur>.github.io/<repo>/`

**Option B — branche dédiée `gh-pages`**
1. Copier uniquement le contenu de `site/` (pas le dossier lui-même) à la
   racine d'une branche `gh-pages`
2. Repo GitHub → Settings → Pages → Source : branche `gh-pages`, dossier `/`

Le fichier `.nojekyll` est déjà présent pour éviter que GitHub Pages
n'essaie de traiter le site avec Jekyll (inutile ici, site 100% statique).

Tous les liens (`index.html`, `terms.html`, `assets/style.css`, ...) sont
en chemins relatifs sans slash de tête : ça fonctionne aussi bien à la
racine du domaine GitHub Pages qu'à une sous-URL (`/<repo>/`).

## Statut

L'adresse de contact dans `terms.html` et `privacy.html` a été renseignée
par le mainteneur du projet. Rien d'autre n'est en attente avant
publication.
