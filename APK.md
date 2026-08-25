# APK y publicación en Google Play

Tu app estará en:  https://ntalex04.github.io/
Package ID a usar: io.github.ntalex04.letrasled   (usa EXACTAMENTE este en PWABuilder)

## 1) Generar el paquete en PWABuilder

1. Publica la app (ver README) y entra a https://www.pwabuilder.com
2. Pega:  https://ntalex04.github.io/  → **Start**.
3. **Package for stores → Android**.
4. En **Package ID / Application ID** escribe:  io.github.ntalex04.letrasled
5. **Signing key: New** → **Generate Package** → descarga el .zip. Contiene:
   - `app-release-signed.apk`  (para instalar/probar en tu celular)
   - `app-release-bundle.aab`  (esto es lo que se sube a Google Play)
   - la huella **SHA-256** y el package.

## 2) Quitar la barra de direcciones (Digital Asset Links)

En este repo, edita `.well-known/assetlinks.json` y pega las huellas SHA-256:

- **Para probar el APK ya:** pega el SHA-256 que te dio PWABuilder en la
  primera línea (`PEGA_AQUI_EL_SHA256_DE_PWABUILDER`).
- **Para Google Play:** cuando publiques, Google RE-FIRMA la app. Copia el
  SHA-256 de **Play Console → tu app → Configuración → Firma de la app
  (App signing key certificate)** y pégalo en la segunda línea
  (`PEGA_AQUI_EL_SHA256_DE_PLAY_APP_SIGNING`).

El package ya está puesto: `io.github.ntalex04.letrasled`.
Guarda, sube el cambio a GitHub, y quedará en:
       https://ntalex04.github.io/.well-known/assetlinks.json
(Por eso conviene el repo en la raíz: la ruta funciona sola.)

## 3) Subir a Google Play

1. Crea la cuenta **Google Play Developer** (pago único de 25 USD).
2. **Create app** → sube el **.aab**.
3. Completa ficha (nombre, ícono, capturas, descripción, política de
   privacidad) y envía a revisión.

## Nota

Para uso personal, el botón **Instalar** de la PWA ya te la deja como app en el
teléfono sin generar nada. El APK/AAB es para **compartir** o **publicar en Play**.
