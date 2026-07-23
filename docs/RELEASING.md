# Publier PasRodave

Le workflow `.github/workflows/release.yml` se déclenche lors de l’envoi d’un
tag au format `1.2.3`.

Il compile l’application, la signe avec Developer ID, la fait notarier par
Apple, crée l’archive signée par Sparkle, publie la GitHub Release puis met à
jour `appcast.xml` sur `main`.

## Secrets GitHub requis

- `DEVELOPER_ID_APPLICATION_P12_BASE64`
- `DEVELOPER_ID_APPLICATION_PASSWORD`
- `BUILD_KEYCHAIN_PASSWORD`
- `APPLE_ID`
- `APPLE_APP_SPECIFIC_PASSWORD`
- `APPLE_TEAM_ID`
- `SPARKLE_PRIVATE_KEY`

La clé privée Sparkle doit correspondre à la clé publique présente dans
`QuickRecorder/Info.plist`. Elle ne doit jamais être ajoutée au dépôt.

## Nouvelle version

1. Mettre à jour `MARKETING_VERSION` et incrémenter
   `CURRENT_PROJECT_VERSION` dans le projet Xcode.
2. Valider la build Release localement.
3. Créer et envoyer le tag :

   ```bash
   git tag -a 1.2.3 -m "PasRodave 1.2.3"
   git push origin 1.2.3
   ```

4. Vérifier la GitHub Release, son archive et le nouvel élément dans
   `appcast.xml`.
