# Entre deux rives — page de test

Trois fichiers :
- `index.html` : la page (thème clair, aucune dépendance sauf la police Google).
- `Code.gs` : le script qui reçoit les réponses dans Google Sheets.
- `LISEZMOI.md` : ces instructions.

## 1. Google Sheets
1. Crée une feuille Google vide (nomme-la « Entre deux rives — réponses »).
2. Extensions > Apps Script. Efface le code existant et colle le contenu de `Code.gs`. Enregistre.
3. Dans la barre du haut, choisis la fonction `setupSheet`, clique Exécuter, accepte les autorisations. Elle crée les onglets « Réponses » et « Synthèse ».
4. Déployer > Nouveau déploiement > type « Application Web ».
   - Exécuter en tant que : **Moi**.
   - Qui a accès : **Tout le monde**.
5. Copie l'URL qui se termine par `/exec`.

## 2. La page
1. Ouvre `index.html`, remplace `COLLE_ICI_L_URL_APPS_SCRIPT` par l'URL copiée.
2. Crée un dépôt GitHub (par exemple `entre-deux-rives`), ajoute `index.html`.
3. Settings > Pages > Source : branche `main`, dossier `/ (root)`. L'adresse sera `https://<ton-pseudo>.github.io/entre-deux-rives/`.

## 3. Tester avant de partager
Ouvre la page, réponds, vérifie qu'une ligne apparaît dans « Réponses » (compte quelques secondes). Supprime cette ligne de test.

## À savoir
- **Anonymat :** la page ne demande ni nom ni e-mail ; le script n'enregistre que les réponses et la date du jour. Si quelqu'un écrit son nom dans le commentaire, il apparaîtra dans la feuille.
- **Un dépôt public rend les extraits publics.** La page contient `noindex` (les moteurs de recherche ne devraient pas la lister), mais quiconque a le lien, ou ouvre le dépôt, peut la lire. N'y mets que des extraits relus.
- **Si tu modifies `Code.gs`,** fais Déployer > Gérer les déploiements > Modifier > Nouvelle version, sinon l'ancienne version reste en ligne.
- **Retour d'envoi :** le navigateur ne peut pas lire la réponse d'Apps Script ; il affiche « Merci » dès que l'envoi part sans erreur réseau. Vérifie toujours le test de l'étape 3.
- **Seuils de l'onglet « Synthèse » :** 10 réponses minimum, 70 % de « oui, sûrement », 40 % prêts à payer, 50 % de lignes de Célia jugées utiles. Ils sont modifiables dans la colonne C.
