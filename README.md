# 🌊 Proyecto Río Cali: Investigación Ambiental y Encuesta Ciudadana

Este repositorio contiene el sitio web interactivo y el sistema de recolección de datos de campo sobre la problemática ambiental y sanitaria en la ronda del **Río Cali (Sector Bulevar del Río, Calle 8ª a Calle 12ª)**.

---

## 📁 Contenido del Repositorio

- `index.html`: Página web completa con diseño responsive, Tailwind CSS, animaciones, mapa interactivo SVG, simulador de franjas horarias y encuesta ciudadana con guardado de respuestas.
- `rio_panoramica.jpg`: Evidencia #01 - Panorámica del cauce y palmas reales.
- `rio_bambu.jpg`: Evidencia #02 - Barrera de bambú y vegetación ribereña.
- `rio_iguana.jpg`: Evidencia #03 - Fauna silvestre (*Iguana iguana*) en riesgo.
- `rio_fuente_basura.jpg`: Evidencia #04 - Insalubridad y colillas en espejos de agua peatonales.
- `video_1.mp4`: Evidencia audiovisual nocturna con marcadores cronológicos.
- `codigo_google_sheets.gs`: Script para registrar automáticamente todas las respuestas de la encuesta en tu propia hoja de Google Sheets.

---

## 🚀 Paso 1: Subir a GitHub y Publicar con GitHub Pages

Para publicar tu página gratis con enlace HTTPS:

1. Crea un nuevo repositorio en tu cuenta de [GitHub](https://github.com/new) (ejemplo: `rio-cali-ambiental`).
2. Sube todos los archivos de esta carpeta a ese repositorio:
   ```bash
   git init
   git add .
   git commit -m "Publicación inicial del proyecto Río Cali"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/rio-cali-ambiental.git
   git push -u origin main
   ```
   *(También puedes arrastrar y soltar los archivos directamente en la interfaz web de GitHub si prefieres).*
3. En tu repositorio en GitHub, ve a **Settings** (Configuración) > **Pages** (en el menú lateral izquierdo).
4. En **Branch**, selecciona `main` y la carpeta `/(root)`, y haz clic en **Save** (Guardar).
5. En 1 minuto tendrás tu enlace público:  
   👉 `https://TU-USUARIO.github.io/rio-cali-ambiental/`

---

## 📊 Paso 2: Conectar la Encuesta para Guardar las Respuestas en Google Sheets

Tu página ya guarda las respuestas automáticamente en el navegador y permite descargarlas en CSV/Excel con un solo clic. Si además quieres que cada respuesta se guarde en tiempo real en una hoja de cálculo en tu Google Drive:

1. Entra a [Google Sheets](https://sheets.new) y crea una nueva hoja (ej: *"Respuestas Encuesta Río Cali"*).
2. En la fila 1 escribe los encabezados de las columnas:
   - **A1:** Marca temporal
   - **B1:** Frecuencia (P1)
   - **C1:** Basuras (P2)
   - **D1:** Canecas (P3)
   - **E1:** Olores / Baño (P4)
   - **F1:** Causa Principal (P5)
   - **G1:** Aporte Opcional
3. En el menú superior de Google Sheets, ve a **Extensiones** > **Apps Script**.
4. Borra el código existente y pega el contenido del archivo `codigo_google_sheets.gs`.
5. Haz clic en el botón azul **Implementar** (arriba a la derecha) > **Nueva implementación**.
6. En el engranaje ⚙️ selecciona tipo: **Aplicación web**.
7. En el campo **"Quién tiene acceso"**, selecciona: **Cualquier persona** (*Anyone*).
8. Haz clic en **Implementar**, autoriza los permisos con tu cuenta de Google y copia la **URL de la aplicación web** que te genera (termina en `/exec`).
9. Abre `index.html` en la línea 1422 y pega tu URL entre las comillas:
   ```javascript
   const GOOGLE_SHEETS_URL = "https://script.google.com/macros/s/TU_CODIGO_AQUI/exec";
   ```
10. Guarda el archivo y haz `git push`. ¡Listo! Cada vez que alguien responda la encuesta en tu web, aparecerá una nueva fila automáticamente en tu Excel de Google Sheets.

---

## 🔒 Privacidad de las Respuestas (Solo Tú Puedes Verlas)

El sistema está configurado para que **ningún visitante del blog pueda ver las respuestas de otras personas**:

1. **Google Sheets (100% Privado por defecto):**
   - La hoja de cálculo se guarda en tu propio Google Drive.
   - Solo tú (iniciando sesión con tu cuenta de Google) tienes permiso para abrirla, ver las filas en tiempo real o descargar el archivo.
   - Los visitantes que llenan la encuesta en tu web solo pueden **enviar** sus respuestas al formulario, nunca leer la hoja.

2. **En la Página Web (Protección por Contraseña):**
   - En el formulario público **se eliminó cualquier botón o tabla visible** de respuestas. Los visitantes solo ven el formulario y el mensaje de confirmación al terminar.
   - En el pie de página (footer) hay un discreto enlace: **`Acceso Privado Administrador 🔒`**.
   - Al hacer clic, solicita una **contraseña** para poder consultar la tabla o descargar el archivo Excel/CSV.
   - **Contraseña por defecto:** `cali2026`  
     *(Puedes cambiarla cuando quieras en el archivo `index.html` en la variable `ADMIN_PASSWORD = "tu_clave"`).*

---

## 🌐 Paso 4: Incrustar en Google Sites

Una vez que tu sitio esté publicado en GitHub Pages:
1. Abre tu [Google Sites](https://sites.google.com).
2. Haz clic en **Insertar** > **Incorporar** (`<>`).
3. Selecciona la pestaña **Mediante URL**.
4. Pega la URL de tu GitHub Pages (`https://TU-USUARIO.github.io/rio-cali-ambiental/`).
5. Elige **"Página completa"** o bloque interactivo e insértala. ¡Todas las imágenes, videos y encuestas funcionarán al 100%!
