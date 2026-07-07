# Una Posibilidad — Cashflow Tambo

App de cash flow mensual (real + proyectado) para gestión tambera. Corre en el navegador, sin servidor. Los meses reales se ven igual en cualquier dispositivo porque quedan embebidos directamente en el archivo; los meses proyectados los editás vos y quedan guardados solo en ese dispositivo/navegador.

## Cómo se actualiza un mes real (flujo mensual)
1. Cuando cierra un mes, mandale a Claude el Excel de ese mes (por este mismo chat).
2. Claude procesa los datos y te devuelve este mismo `index.html`, con ese mes agregado como dato real embebido (y la ventana de 6 meses proyectados corrida para adelante).
3. Subís ese `index.html` al repositorio de GitHub, pisando el anterior (Add file → Upload files).
4. Listo — cualquiera que entre al link ya ve ese mes como real, sin tocar nada más.

Los meses proyectados (estimados) los seguís editando vos mismo directo en la app, en cualquier dispositivo — esos cambios quedan guardados solo en ese navegador. Si querés pasar tus proyecciones de un dispositivo a otro, usá los botones **"Exportar copia"** / **"Importar copia"** dentro de la app.

## Archivos
- `index.html` — la app completa (HTML + CSS + JS + gráficos embebidos, más los datos reales embebidos). Es el único archivo necesario para que funcione.
- `manifest.json`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — para poder "instalarla" como app en el celular/PC con el logo de la empresa.

## Cómo subirlo a GitHub (una sola vez)

### Opción A — Desde la web de GitHub (más simple, sin instalar nada)
1. Entrá a [github.com](https://github.com) e iniciá sesión (o creá una cuenta gratis).
2. Arriba a la derecha, tocá el **+** → **New repository**.
3. Ponele un nombre. Dejalo **Public** (necesario para que GitHub Pages sea gratis). Creá el repositorio.
4. Adentro del repo, tocá **Add file → Upload files**.
5. Arrastrá los 5 archivos de esta carpeta (`index.html`, `manifest.json`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`) y confirmá el commit ("Commit changes").
6. Andá a **Settings → Pages** (menú de la izquierda).
7. En "Build and deployment" → **Source**, elegí **Deploy from a branch**. En "Branch" elegí `main` y la carpeta `/ (root)`. Guardá.
8. Esperá 1-2 minutos: GitHub te va a mostrar la URL pública, algo como:
   `https://tu-usuario.github.io/nombre-repo/`

### Opción B — Con git desde la terminal
```bash
git init
git add .
git commit -m "Una Posibilidad - cashflow tambo"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/una-posibilidad.git
git push -u origin main
```
Después activá GitHub Pages igual que en el paso 6-8 de la Opción A.

## Agregarla a la pantalla de inicio (como app)
- **Android (Chrome):** abrí la URL, tocá el menú (⋮) → "Agregar a pantalla de inicio".
- **iPhone (Safari):** abrí la URL, tocá el botón de compartir → "Agregar a la pantalla de inicio".

## Actualizaciones futuras
Para un mes real nuevo: mandale el Excel a Claude por el chat, y subí el `index.html` que te devuelve. Para cualquier otro cambio (diseño, funciones nuevas, etc.), pedíselo a Claude igual y volvé a subir el archivo actualizado.
