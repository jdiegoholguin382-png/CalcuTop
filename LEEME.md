# CalcuTop 1.0 — Proyecto Android

Calculadora topográfica de campo de **CONSTRUTOP M&T S.A.S**.
Funciona sin internet: los cálculos, la letra de los números y el logo van dentro de la app.

## Qué hay en esta carpeta

- `www/` — la app (index.html y la letra JetBrains Mono).
- `resources/android/res/` — ícono y pantalla de inicio con el logo de CONSTRUTOP.
- `capacitor.config.json` — nombre (CalcuTop) e identificador (co.construtop.calcutop).
- `.github/workflows/compilar-apk.yml` — compila el APK en GitHub, gratis y en la nube.

---

## Opción A (recomendada): que GitHub compile el APK

No necesitas instalar nada en tu computador.

1. Crea una cuenta gratis en https://github.com (si no tienes).
2. Arriba a la derecha toca **+ → New repository**. Nombre: `CalcuTop`. Puede ser **Private**. Toca **Create repository**.
3. En la página del repositorio toca **uploading an existing file**.
4. Descomprime este ZIP en tu computador y **arrastra todo el contenido de la carpeta CalcuTop** (incluida la carpeta `.github`) a la página. Toca **Commit changes**.
   - Si la carpeta `.github` no se sube (en algunos sistemas está oculta): toca **Add file → Create new file**, escribe como nombre `.github/workflows/compilar-apk.yml`, pega el contenido de ese archivo y toca **Commit changes**.
5. Ve a la pestaña **Actions**. Verás "Compilar APK CalcuTop" trabajando (unos 5 a 8 minutos). Cuando salga el visto verde, terminó.
6. Ve a **Releases** (columna derecha de la página principal del repositorio) → **CalcuTop 1.0** → descarga **CalcuTop-1.0.apk** desde el celular.

Cada vez que cambies un archivo y lo subas, GitHub vuelve a compilar el APK solo.

## Opción B: compilar en tu computador con Android Studio

Necesitas Node.js 20 (https://nodejs.org) y Android Studio (https://developer.android.com/studio).
En una terminal, dentro de la carpeta CalcuTop:

```
npm install
npx cap add android
```
Copia el contenido de `resources/android/res/` dentro de `android/app/src/main/res/` (reemplaza los archivos). Luego:
```
npx cap sync android
npx cap open android
```
En Android Studio: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
El APK queda en `android/app/build/outputs/apk/debug/app-debug.apk`.

---

## Instalar en el celular

1. Abre el archivo **CalcuTop-1.0.apk** en el teléfono.
2. Android pedirá permiso para **instalar apps de origen desconocido** desde el navegador o el administrador de archivos: actívalo solo para esa app.
3. Toca **Instalar**. Aparecerá el ícono de CalcuTop.

Es un APK de prueba firmado automáticamente: sirve para instalar en tus celulares y los de tu equipo. Para publicarlo en Google Play se necesita una firma propia; eso se puede preparar después.

## Importante sobre los datos

- La lista de puntos y lo que escribes se guarda **dentro de la app, en ese celular**.
- Si desinstalas la app o borras sus datos en Ajustes, se pierden. Antes, usa **Puntos → Exportar lista** y guarda el texto.
- Al actualizar el APK (instalar una versión nueva encima), los datos se conservan.

© 2026 CONSTRUTOP M&T S.A.S
