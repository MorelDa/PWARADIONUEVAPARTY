# RADIO PARTY - PWA Profesional

Aplicación web progresiva (PWA) instalable en **Android, iOS, Windows, Mac y Linux**.

## Características

- Reproductor de radio en vivo con visualizador de audio en tiempo real
- **Instalable** en Android, iOS y PC (sin tiendas de aplicaciones)
- Funciona **offline** (interfaz cacheada, gracias al Service Worker)
- **Compartir en múltiples redes**: WhatsApp, Facebook, Twitter/X, Telegram, Messenger, Email, SMS y copiar enlace
- Color dinámico extraído automáticamente del logo
- Media Session API (controles en pantalla de bloqueo)
- Panel de administración para cambiar la configuración sin tocar código
- Código JavaScript **ofuscado** (dificulta la copia y protege la lógica)

## Estructura del proyecto

```
pwa-radio-pro/
├── index.html         # Página principal del reproductor
├── admin.html         # Panel para generar config.json
├── style.css          # Estilos separados
├── app.min.js         # JavaScript ofuscado (código fuente protegido)
├── config.json        # Configuración editable
├── manifest.json      # Manifest de la PWA
├── sw.js              # Service Worker (offline + install)
└── icons/
    ├── icon-192.png
    ├── icon-512.png
    └── icon-maskable-512.png
```

## Instalación

### En un servidor web (recomendado)
1. Sube todos los archivos a tu hosting (Netlify, Vercel, GitHub Pages, cPanel, etc.)
2. La URL **debe ser HTTPS** (obligatorio para PWA e install prompt)
3. Abre la URL desde tu móvil o PC → aparecerá el botón **"Instalar"**

### GitHub Pages (gratis)
1. Sube todo a tu repo `PWARADIONUEVAPARTY`
2. Ve a **Settings → Pages** → Source: `main` → root
3. Abre `https://TU-USUARIO.github.io/PWARADIONUEVAPARTY/`

## Cómo se instala en cada plataforma

| Plataforma | Cómo instalar |
|-----------|---------------|
| **Android** (Chrome) | Botón "Instalar" en la app, o menú de Chrome → "Instalar aplicación" |
| **iOS** (Safari) | Botón "Compartir" → "Añadir a pantalla de inicio" |
| **Windows / Mac / Linux** (Chrome/Edge) | Ícono de instalación en la barra de direcciones, o menú → "Instalar RADIO PARTY" |

## Cambiar la configuración

1. Abre `admin.html` en el navegador (`https://tudominio.com/admin.html`)
2. Modifica los campos
3. Pulsa **"Generar JSON"** → se descargará `config.json`
4. Sube ese archivo a la raíz de tu proyecto sustituyendo el anterior
5. Recarga la página del reproductor

## Tecnología

Construido con **HTML5 + CSS3 + JavaScript ES6 (Vanilla)** — la mejor combinación para una PWA porque:
- Sin frameworks pesados (Angular/React/Vue son innecesarios aquí)
- Sin bundlers (funciona directamente al subirlo al servidor)
- Máximo rendimiento en móviles
- 100% compatible con todos los navegadores modernos

## Protección de código

El archivo `app.min.js` está **ofuscado con nivel alto**:
- Nombres de variables y funciones hexadecimales
- Strings codificados en Base64
- Control-flow flattening
- Dead code injection
- Self-defending (se rompe si alguien lo formatea)

Adicionalmente, en `index.html` se deshabilitan:
- Menú contextual (clic derecho)
- Atajos de DevTools (F12, Ctrl+Shift+I, Ctrl+U)
- Selección de texto

> Nota: Ningún código JavaScript ejecutado en el navegador es 100% imposible de copiar, pero estas medidas dificultan enormemente la ingeniería inversa.

## Licencia

Copyright (c) 2026 - Todos los derechos reservados.
