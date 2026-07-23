<p align="center">
  <img src="./QuickRecorder/Assets.xcassets/AppIcon.appiconset/icon_128x128@2x.png" width="200" height="200" alt="Icône de PasRodave" />
</p>

<h1 align="center">PasRodave</h1>

<p align="center">
  Enregistreur d’écran et d’audio léger pour macOS.
</p>

PasRodave permet d’enregistrer un écran, une fenêtre, une application, une zone
ou uniquement le son du Mac. Le logo original a été conservé.

## Particularités de cette version

- enregistrement MP3 direct, sans longue conversion après l’arrêt ;
- capture native du microphone avec ScreenCaptureKit sous macOS 15 et versions
  ultérieures ;
- meilleure stabilité avec les AirPods et les appels WhatsApp ;
- microphone activé par défaut avec le micro du Mac comme choix initial ;
- recherche quotidienne des nouvelles versions GitHub avec confirmation avant
  installation ;
- commande manuelle **Check for Updates…** disponible dans l’application.

## Installation

Téléchargez la dernière version depuis
[GitHub Releases](https://github.com/Pythagorrre/PasRodave/releases).

La première installation de PasRodave doit être effectuée manuellement. Les
versions suivantes pourront être proposées et installées par le mécanisme de
mise à jour intégré.

## Compilation

Le projet nécessite Xcode et macOS 12.3 ou une version ultérieure.

```bash
git clone https://github.com/Pythagorrre/PasRodave.git
cd PasRodave
xcodebuild \
  -project QuickRecorder.xcodeproj \
  -scheme QuickRecorder \
  -configuration Release \
  CODE_SIGNING_ALLOWED=NO \
  build
```

## Mises à jour

PasRodave utilise [Sparkle](https://sparkle-project.org/) et un flux signé propre
à l’application :

`https://raw.githubusercontent.com/Pythagorrre/PasRodave/main/appcast.xml`

La clé privée Sparkle n’est jamais enregistrée dans le dépôt. La procédure de
publication est décrite dans [docs/RELEASING.md](docs/RELEASING.md).

## Origine et licence

PasRodave est basé sur
[QuickRecorder](https://github.com/lihaoyun6/QuickRecorder), créé par
lihaoyun6. Le code reste distribué sous licence
[GNU AGPL v3](LICENSE), conformément au projet d’origine.
