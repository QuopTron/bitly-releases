# bitly-releases

Binarios publicados de **Bitly** (Android, Windows, macOS, iOS y PWA).

Este repo **no tiene código**: es el espejo público de las releases del proyecto.
El código vive en el repo privado `QuopTron/bitly`.

## ¿Por qué existe?

El repo del código es privado, y en GitHub los assets de una release privada solo
se pueden descargar con un token. Ni la app ni el sitio web pueden llevar uno
dentro (viajan dentro de un APK o de una página pública, cualquiera los puede
leer), así que antes no tenían forma de ofrecer las descargas.

Acá la API pública de GitHub responde sin autenticación y cada binario se baja
por URL directa. App y sitio leen siempre desde acá, así que muestran la misma
versión.

## Qué hay en cada release

| Archivo | Plataforma |
|---|---|
| `app-arm64-v8a-release.apk` | Android, celulares modernos (2016 en adelante) |
| `app-armeabi-v7a-release.apk` | Android, celulares antiguos |
| `app-x86_64-release.apk` | Android, emuladores y Chromebooks |
| `Bitly-Setup-X.Y.Z.exe` | Windows x64 (Intel/AMD) |
| `Bitly-Setup-X.Y.Z-arm64.exe` | Windows ARM64 |
| `Bitly-X.Y.Z-macos.dmg` | macOS (Apple Silicon) |
| `Bitly-X.Y.Z-ios.ipa` | iOS (sin firmar: instalable con TrollStore) |
| `bitly-pwa-X.Y.Z.zip` | PWA para TVs y navegadores |

## Descargar la última versión

- Página de releases: <https://github.com/QuopTron/bitly-releases/releases>
- API (JSON, sin autenticación): <https://api.github.com/repos/QuopTron/bitly-releases/releases/latest>
- Sitio oficial: <https://bitly.app>

## Cómo se publica

Las releases se crean primero en el repo privado (fuente de verdad) y un workflow
de GitHub Actions copia los binarios acá, con el mismo tag. Cada release nueva
sale con las plataformas que se compilaron; si a alguna le falta el binario, el
sitio y la app ofrecen automáticamente la última versión que sí lo tenga.
