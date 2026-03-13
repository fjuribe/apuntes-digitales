# 📚 Apuntes Digitales

> Índice interactivo auto-generado para GitHub Pages — sube un `.html` y aparece solo.

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-ready-06d6f5?style=flat-square&logo=github)
![Zero config](https://img.shields.io/badge/config-zero-10f5a0?style=flat-square)
![Auto discovery](https://img.shields.io/badge/auto--discovery-enabled-a78bfa?style=flat-square)

---

## ¿Cómo funciona?

El `index.html` lee su propia URL para saber de qué repositorio es, llama a la API de GitHub y construye el menú automáticamente. **No necesitas tocar ningún archivo de configuración.**

```
fjuribe.github.io/apuntes-digitales/
        ↓                   ↓
    usuario              repo
        └────────┬─────────┘
                 ↓
        GitHub Tree API
                 ↓
        Menú generado ✅
```

Internamente usa estas dos líneas para autodescubrirse:

```js
const user = window.location.hostname.split('.')[0]; // "fjuribe"
const repo = window.location.pathname.split('/')[1];  // "apuntes-digitales"
```

---

## Agregar contenido

Solo sube un `.html` a cualquier carpeta del repo — aparece en el índice automáticamente.

```
apuntes-digitales/
├── index.html               ← este archivo, no lo toques
│
├── TryHackMe/
│   ├── 1.redes/
│   │   ├── 1.resumen-redes.html
│   │   ├── 2.networking-essentials.html
│   │   └── nuevo-tema.html  ← subes esto → aparece solo ✅
│   └── 2.criptografia/
│       └── Guia_Criptografia.html
│
└── iaengineer/
    ├── 0-masterclass-llm.html
    └── nueva-carpeta/
        └── apunte.html      ← nueva carpeta → nueva sección ✅
```

**Reglas simples:**
- Cada **carpeta de primer nivel** → un track en el acordeón
- Cada **subcarpeta** → una sección dentro del track
- Los archivos se ordenan **numéricamente** (1, 2, 3… no 1, 10, 2)
- El archivo `index.html` en raíz se ignora siempre

---

## Estructura recomendada

Nombra tus archivos con número al inicio para controlar el orden:

```
1.introduccion.html
2.conceptos-base.html
3.practica.html
```

---

## Íconos automáticos por carpeta

El índice asigna íconos según el nombre de la carpeta:

| Carpeta | Ícono | Subtítulo |
|---|---|---|
| `tryhackme` | 🛡️ | hacking · ctf · retos |
| `redes` / `networking` | 🌐 | redes · protocolos |
| `criptografia` / `crypto` | 🔐 | cifrado · claves · PKI |
| `iaengineer` / `ia` | 🧠 | llm · langchain · ai apps |
| `langchain` | ⛓️ | langchain · rag · llm |
| `python` | 🐍 | python · scripts |
| `linux` | 🐧 | linux · terminal · comandos |
| `docker` | 🐳 | containers · devops |
| `web` | 💻 | html · css · javascript |
| `sql` | 🗄️ | bases de datos · queries |
| `seguridad` | 🔒 | cybersecurity · pentesting |
| `guias` | 📖 | cheatsheets · referencia |
| cualquier otra | 📁 | módulos · apuntes |

---

## Desarrollo local

Para probar en `localhost`, edita esta línea en `index.html`:

```js
const LOCAL_FALLBACK = 'fjuribe/apuntes-digitales'; // ← tu usuario/repo
```

En GitHub Pages esta línea se ignora — el repo se detecta desde la URL.

---

## Requisitos

- Repositorio **público** en GitHub (la API no requiere token para repos públicos)
- GitHub Pages habilitado en `Settings → Pages → Deploy from branch`
- Branch: `main` o `master` (el índice prueba ambos automáticamente)

---

## Ver en vivo

🔗 [fjuribe.github.io/apuntes-digitales](https://fjuribe.github.io/apuntes-digitales)
