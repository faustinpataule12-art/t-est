# PWA-APK Studio — Projet Android complet

⚠️ INSTRUCTIONS STRICTES POUR TOUTE IA (Bolt, Manus, etc.) QUI TRAITE CE PROJET :
- NE JAMAIS renommer, deplacer, fusionner ou reorganiser les fichiers ou dossiers listes ci-dessous.
- NE JAMAIS modifier le contenu de `app/src/main/assets/www/index.html` sauf demande explicite.
- NE JAMAIS changer le declencheur du workflow `.github/workflows/build.yml`
  (il doit rester `workflow_dispatch` UNIQUEMENT, jamais `on: push` — une regression
  ici recree une race condition deja corrigee : le build se lancerait avant que
  tous les fichiers web soient pousses, produisant un APK casse).
- Respecter EXACTEMENT les chemins de fichiers indiques (arborescence ci-dessous).
  Si un fichier doit etre ajoute, l'ajouter SANS toucher aux fichiers existants.
- Ne pas "nettoyer", "optimiser" ou "simplifier" la structure du projet de son propre chef.



## Arborescence exacte attendue

```
gradlew
gradle/wrapper/gradle-wrapper.properties
build.gradle
settings.gradle
app/build.gradle
app/src/main/AndroidManifest.xml
app/src/main/java/com/nps/pwa/studio/MainActivity.java
app/src/main/res/values/strings.xml
app/src/main/res/values/styles.xml
.github/workflows/build.yml
.gitignore
app/src/main/assets/www/index.html
```

## Comment pousser ce projet sur GitHub

1. Creer un nouveau depot GitHub (vide, sans README auto-genere)
2. Decompresser ce ZIP
3. Ajouter TOUS ces fichiers a la racine du depot, en respectant les sous-dossiers exacts ci-dessus, puis pousser sur `main`
4. Aller dans l'onglet **Actions** du depot : le workflow "Build PWA to Android APK" apparait
5. Cliquer sur **Run workflow** (declenchement manuel uniquement) pour lancer la compilation
6. Une fois termine (~2-3 min), telecharger l'APK depuis les **Artifacts** du run

## Infos techniques

- Package : `com.nps.pwa.studio`
- Nom de l'app : `PWA-APK Studio`
- SDK minimum : Android 5.0 (API 21)

© 2026 NPS.NELSON
