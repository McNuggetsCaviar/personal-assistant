# Le Grand Bal Masqué — site

Site statique (une seule page `index.html`) pour l'invitation au Grand Bal masqué.
Prêt à être déployé sur **Vercel**.

## Aperçu local

Ouvrez simplement `index.html` dans un navigateur, ou servez le dossier :

```bash
python3 -m http.server 8000
# puis http://localhost:8000
```

## Déploiement sur Vercel

Le dépôt est déjà configuré (`vercel.json`). Aucun réglage de build n'est
nécessaire : Vercel sert `index.html` directement.

### Option A — via l'interface Vercel (recommandé)

1. Aller sur https://vercel.com/new
2. « Import Git Repository » → choisir `McNuggetsCaviar/personal-assistant`
3. Framework Preset : **Other** (laisser tel quel)
4. Cliquer sur **Deploy**

Le site est en ligne en quelques secondes. Chaque `git push` redéploie
automatiquement.

### Option B — via la CLI Vercel

```bash
npm i -g vercel
vercel        # déploiement de prévisualisation
vercel --prod # déploiement en production
```
