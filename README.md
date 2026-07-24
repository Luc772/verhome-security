# VERHOME SECURITY — Sitio web

Sitio estático (HTML/CSS/JS puro, sin frameworks ni build) con 3 divisiones:
1. **Seguridad** (etapas: kits de cámaras IP/WiFi/Análogas → alarmas hogar/comercio/comunitarias → internet Starlink/router)
2. **Electricidad** (instalaciones domiciliarias, automatización de portones, fotovoltaico)
3. **Industrial** (trifásicas, motores, generadores, tableros, mantención)

Listo para publicar en GitHub Pages.

## Cómo publicarlo en GitHub Pages

1. **Crea un repositorio en GitHub**
   - Entra a https://github.com/new
   - Nombre sugerido: `camaras-seguridad` (puede ser el que quieras)
   - Déjalo público
   - No agregues README ni .gitignore ahí (ya los traemos)

2. **Sube estos archivos al repositorio**

   Desde tu computador, en la carpeta donde tengas `index.html` y este `README.md`:

   ```bash
   git init
   git add .
   git commit -m "Primer sitio: catálogo de cámaras"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/camaras-seguridad.git
   git push -u origin main
   ```

   Reemplaza `TU-USUARIO` por tu nombre de usuario de GitHub.

3. **Activa GitHub Pages**
   - Ve a tu repositorio en GitHub → pestaña **Settings**
   - En el menú lateral, entra a **Pages**
   - En "Build and deployment" → **Source**, elige **Deploy from a branch**
   - En **Branch**, selecciona `main` y carpeta `/ (root)` → **Save**

4. **Espera 1-2 minutos**
   - GitHub te dará una URL como:
     `https://TU-USUARIO.github.io/camaras-seguridad/`
   - Esa es tu página en vivo. Cada vez que hagas `git push`, se actualiza sola.

## Estructura

```
camaras-site/
├── index.html   → toda la página (catálogo, kits, contacto)
└── README.md    → este archivo
```

## Personalizar

- **Productos de Seguridad**: edita los arreglos `renderCards('grid-camaras', ...)`, `grid-alarmas` y `grid-internet` dentro de `<script>` en `index.html`.
- **Servicios de Electricidad e Industrial**: son tarjetas fijas en HTML, dentro de `<section id="electricidad">` y `<section id="industrial">`. Edita directamente el texto de cada `.service-card`.
- **Colores**: variables al inicio del `<style>` (`--bg`, `--amber`, etc.).
- **Textos de contacto**: sección `#contacto`, cambia correo, teléfono y horario.
- **Formulario**: hoy solo muestra una alerta al enviar. Si quieres que llegue a tu correo de verdad, te recomiendo conectar un servicio como Formspree o Getform (ambos tienen plan gratis y no requieren backend propio).

## Próximos pasos sugeridos

- Reemplazar los precios de ejemplo por tus precios reales.
- Agregar fotos reales de instalaciones (hoy los "feeds" son ilustrativos, no fotos).
- Si cada división crece mucho, se puede separar en 3 páginas (`seguridad.html`, `electricidad.html`, `industrial.html`) enlazadas desde el menú, en vez de anclas en una sola página.
