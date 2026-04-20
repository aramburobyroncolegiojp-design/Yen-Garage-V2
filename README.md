# Yen Garage — Control Operativo v4

Sistema de control de rentabilidad y cotizaciones para talleres automotrices.
Construido como aplicacion web progresiva (PWA) — funciona desde el navegador
y puede instalarse en el celular sin App Store.

---

## Estructura del proyecto

```
yen-garage/
│
├── index.html          ← Estructura HTML principal (toda la UI)
│
├── css/
│   ├── reset.css       ← Variables globales, reset, tipografia base
│   ├── layout.css      ← Shell, header, nav inferior, scroll area
│   ├── components.css  ← Componentes reutilizables (cards, botones, modales...)
│   ├── pages.css       ← Estilos especificos por pagina
│   └── responsive.css  ← Breakpoints: movil, tablet, desktop
│
├── js/
│   ├── db.js           ← Capa de datos (localStorage — facil de migrar)
│   ├── utils.js        ← Funciones compartidas (formato, calculos, DOM helpers)
│   ├── registro.js     ← Logica de la pagina de Registro / Rentabilidad
│   ├── cotizacion.js   ← Logica de la pagina de Cotizacion
│   ├── historial.js    ← Dashboard, listas, modal de detalle, eliminacion
│   └── app.js          ← Inicializacion y navegacion
│
├── assets/
│   ├── icon-192.png    ← Icono PWA (192x192 px)
│   └── icon-512.png    ← Icono PWA (512x512 px)
│
├── manifest.json       ← Configuracion PWA (instalar en pantalla de inicio)
└── README.md           ← Este archivo
```

---

## Como abrirlo en VS Code

1. Abre VS Code
2. Archivo > Abrir carpeta > selecciona la carpeta `yen-garage`
3. Instala la extension **Live Server** (ritwickdey.LiveServer)
4. Click derecho en `index.html` > **Open with Live Server**
5. Se abre en el navegador con recarga automatica al editar

---

## Como subirlo a produccion (gratis, 5 minutos)

### Opcion A — Netlify Drop (sin cuenta, inmediato)
1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `yen-garage` completa
3. Netlify te da una URL publica en segundos
4. Listo — comparte el link con quien necesites

### Opcion B — Netlify + GitHub (recomendado para actualizaciones)
1. Sube el proyecto a un repositorio en GitHub
2. En Netlify: New site > Import from Git > conecta el repo
3. Build command: (dejar vacio)
4. Publish directory: `.` (o `yen-garage` si es subcarpeta)
5. Cada `git push` actualiza el sitio automaticamente

### Opcion C — GitHub Pages
1. Sube el proyecto a GitHub
2. Settings del repo > Pages > Source: `main branch / root`
3. URL: `https://tu-usuario.github.io/yen-garage`

---

## Como instalarlo como app en el celular

Una vez subido a Netlify o GitHub Pages:

**En iPhone (Safari):**
1. Abre la URL en Safari
2. Toca el boton de compartir (cuadrado con flecha)
3. "Agregar a pantalla de inicio"
4. Aparece como app con icono propio

**En Android (Chrome):**
1. Abre la URL en Chrome
2. Menu (tres puntos) > "Instalar aplicacion" o "Agregar a pantalla de inicio"
3. Funciona igual que una app nativa

---

## Como personalizar

### Cambiar el nombre del taller
En `index.html`, busca:
```html
<div class="brand">YEN <span>GARAGE</span></div>
```
Cambia el texto por el nombre de tu taller.

### Cambiar el color de acento (naranja)
En `css/reset.css`, busca:
```css
--accent: #c1440e;
```
Cambia el valor hexadecimal por el color que prefieras.

### Agregar tipos de trabajo
En `index.html`, dentro del select `r-tipo`, agrega:
```html
<option>Tu nuevo tipo de trabajo</option>
```

---

## Migrar los datos a la nube (paso siguiente)

Los datos actualmente se guardan en `localStorage` del navegador.
Para sincronizar entre dispositivos, el paso siguiente es conectar
a **Supabase** (https://supabase.com — gratuito hasta cierto volumen).

En `js/db.js` esta toda la capa de datos centralizada.
Solo hay que reemplazar las llamadas a `localStorage` por
llamadas a la API REST de Supabase — sin tocar el resto del codigo.

---

## Soporte de navegadores

| Navegador       | Soporte |
|-----------------|---------|
| Chrome 90+      | Total   |
| Safari 14+      | Total   |
| Firefox 88+     | Total   |
| Edge 90+        | Total   |
| Chrome Android  | Total   |
| Safari iOS 14+  | Total   |

---

Yen Garage v4 — 2024
