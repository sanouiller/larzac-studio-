# Larzac Studio — Digital Slate v1.0

Application de clap numérique, en HTML/CSS/JavaScript, sans dépendances externes. Compatible avec GitHub Pages et utilisable hors ligne après le premier chargement.

## Publication sur GitHub Pages

1. Créer un dépôt public `larzac-digital-slate` sur GitHub.
2. Envoyer **le contenu de ce dossier** à la racine du dépôt (`index.html`, `app.js`, `style.css`, `sw.js`, `manifest.webmanifest` et `assets/`).
3. Dans **Settings → Pages**, sélectionner **Deploy from a branch**, puis `main` et `/ (root)`, et enregistrer.
4. Ouvrir l'adresse fournie par GitHub Pages, par exemple `https://UTILISATEUR.github.io/larzac-digital-slate/`.
5. Sur mobile, utiliser « Ajouter à l'écran d'accueil » ou « Installer l'application » selon le navigateur. L'installation dépend du navigateur et du système ; l'application reste utilisable comme site web.

## Utilisation

Dans **Régie**, renseigner les informations et choisir le signal sonore. Cliquer sur **Ouvrir le clap**, puis sur **CLAP !** : un compte à rebours 3–2–1 précède le son et le flash. Cliquer sur **Valider et préparer la suite** pour activer la prochaine prise. Dans **Historique**, évaluer les prises et exporter le CSV.

Les données sont stockées dans le `localStorage` du navigateur. Elles ne sont **pas synchronisées entre appareils** et peuvent disparaître si les données du site sont effacées ou en navigation privée. Exporter régulièrement le CSV. Le stockage local est limité par le navigateur.

L'horloge affiche l'heure locale avec un nombre de fractions calculé selon la cadence choisie. **Il ne s'agit pas d'un timecode matériel synchronisé**. Le son synthétique, le flash de l'écran et leur captation peuvent avoir une latence variable. Un écran ne remplace pas nécessairement un clap physique pour une synchronisation précise.

Le plein écran et l'installation PWA varient selon les navigateurs, notamment sur iOS. La mise en cache hors ligne nécessite un premier chargement réussi sur HTTPS. L'orientation paysage est recommandée, sans verrouillage forcé.

## Mise à jour

En cas de modification des fichiers, changer la constante `CACHE` dans `sw.js` (par exemple `larzac-slate-v1.0.1`) pour invalider l'ancien cache PWA.

## Technique

Aucun service distant, aucune bibliothèque, aucun compte. Horloge en heure locale, interface responsive, son généré via Web Audio API, historique local et export CSV UTF-8 avec séparateur point-virgule.
