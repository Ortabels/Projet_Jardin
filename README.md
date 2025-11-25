# Ortabels — Hugo + Decap CMS (Netlify)

Ce dossier est un squelette de site pour l'association **Ortabels** :

- Site statique Hugo.
- Projets stockés dans `content/projects/` sous forme de fichiers Markdown.
- Chaque projet contient :
  - une partie **publique** (affichée sur le site),
  - une section `# INTERNAL` avec le cahier des charges complet (non affichée sur le site).
- Une interface d'administration (Decap CMS) accessible via `/admin/`.

## Lancer en local

1. Installer Hugo (version étendue de préférence).
2. Dans ce dossier, lancer :

```bash
hugo server -D
```

3. Ouvrir dans le navigateur :  
   - Site : http://localhost:1313/  
   - Admin : http://localhost:1313/admin/

En mode local, `local_backend: true` permet de tester le CMS sans Netlify.

## Déploiement sur Netlify

1. Pousser ce dossier dans un dépôt Git (GitHub, GitLab, etc.).
2. Créer un site sur Netlify et le connecter au dépôt.
3. Paramétrer :
   - **Build command** : `hugo`
   - **Publish directory** : `public`
4. Activer **Netlify Identity** puis **Git Gateway**.
5. Ajouter les utilisateurs (membres Ortabels) via Netlify Identity.
6. Ils pourront ensuite se connecter sur :  
   `https://votre-site.netlify.app/admin/`

## Édition des projets

- Les fichiers projets sont dans `content/projects/*.md`.
- Via le CMS (admin), les membres peuvent :
  - créer un projet,
  - modifier le titre, la date, le statut, etc.,
  - éditer le contenu Markdown.

### IMPORTANT

- La partie **publique** est tout ce qui se trouve au-dessus de la ligne :

  `---`

  qui précède `# INTERNAL`.

- Tout ce qui se trouve sous `# INTERNAL` est un cahier des charges interne
  (budget détaillé, suivi CA, etc.) :
  - il reste dans le fichier,
  - il est masqué dans le site public par le template Hugo.

Vous pouvez adapter les modèles et le thème selon l'évolution de l'association.
