# LogéTud Rabat – APK Android

Ce projet transforme l'application LogéTud Rabat en application Android (APK).
L'application est dans `app/src/main/assets/index.html` et s'ouvre dans une WebView.

## Option 1 : compiler automatiquement sur GitHub (recommandé)

1. Créez un dépôt GitHub vide (par exemple `logetud-android`).
2. Envoyez tous les fichiers de ce dossier dans le dépôt, à la racine :
   ```
   git init
   git add .
   git commit -m "LogéTud Android"
   git branch -M main
   git remote add origin https://github.com/VOTRE-NOM/logetud-android.git
   git push -u origin main
   ```
   (Vous pouvez aussi glisser-déposer les fichiers sur la page GitHub, en gardant la structure des dossiers.)
3. Allez dans l'onglet **Actions** du dépôt. Le workflow « Build Android APK » se lance tout seul.
4. Une fois terminé (environ 3 à 5 minutes), ouvrez l'exécution et téléchargez **LogeTud-debug-apk** dans la section *Artifacts*.
5. Décompressez le fichier : vous obtenez `app-debug.apk`.
6. Copiez-le sur votre téléphone Android et installez-le. Il faut autoriser l'installation depuis une source inconnue.

Vous pouvez aussi relancer la compilation à tout moment avec **Actions → Build Android APK → Run workflow**.

## Option 2 : compiler avec Android Studio

1. Ouvrez Android Studio, puis **Open** et choisissez ce dossier.
2. Attendez la synchronisation Gradle.
3. Menu **Build → Build Bundle(s) / APK(s) → Build APK(s)**.

## Remarques

- L'APK généré est une version **debug** : elle s'installe sur les téléphones, mais elle n'est pas prête pour le Google Play Store.
- Pour publier sur le Play Store, il faut générer une version **release signée** avec votre propre clé (fichier `.keystore`). Ne la mettez pas sur GitHub.
- L'application demande l'accès à Internet, uniquement pour charger la police Google Fonts. Sans connexion, elle fonctionne quand même avec une police de remplacement.
- Les données (comptes, favoris) sont stockées sur le téléphone, dans l'application. Elles sont effacées si l'application est désinstallée.
- Identifiant de l'application : `rabat.logetud`. Vous pouvez le changer dans `app/build.gradle` et dans le fichier `AndroidManifest.xml`.
