# ecobraids-beacons

Sitio estatico mobile-first para Beacons con tabs de servicios, acordeones por estilo y datos cargados desde JSON.

## Estructura

```text
public/index.html
public/data/servicios.json
data/servicios.json
firestore/schema.json
package.json
vercel.json
```

`data/servicios.json` es la referencia editable. `public/data/servicios.json` existe para que `fetch('./data/servicios.json')` funcione con `http-server public/` y Vercel sin build.

## Local

```bash
npm install
npm run dev
```

Abre `http://localhost:8080`.

## Build

```bash
npm run build
```

El build copia `public/` a `dist/`.

## Deploy en Vercel

1. Sube el repo a GitHub.
2. Importa el repo en Vercel.
3. Usa framework preset `Other`.
4. Build command: vacio.
5. Output directory: `public`.

`vercel.json` sirve `/data/servicios.json` como JSON y redirige el resto a `index.html`.

## Firestore

Referencia de escritura:

```text
/leads/{timestamp}
```

Campos esperados:

```json
{
  "estilo": "EcoBraids",
  "email": "cliente@email.com",
  "mensaje": "Hola, quiero consultar por EcoBraids.",
  "timestamp": "2026-07-03T12:00:00.000Z",
  "source": "beacons"
}
```

## Ajustes rapidos

- Cambia el link de Instagram en `public/index.html`, constante `INSTAGRAM_DM_URL`.
- Edita servicios y precios en `data/servicios.json` y replica el cambio en `public/data/servicios.json` antes de publicar sin build.
