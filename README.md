# Post-contenido — Unidad 2: HTML5 Básico

**Autor:** Samuel García — Ingeniería de Sistemas, Séptimo Semestre (2026)

## Descripción
Repositorio del laboratorio de la Unidad 2 de Programación Web —
Séptimo Semestre. Contiene dos partes: página de portafolio con
etiquetas semánticas de HTML5 (`parte-1-pagina-semantica/`) y
formulario de registro con validación nativa HTML5
(`parte-2-formulario-registro/`).

## Estructura del repositorio
```
├── parte-1-pagina-semantica/
│   ├── index.html
│   ├── img/
│   │   ├── perfil.png
│   │   └── captura-01.png
│   └── audio/
│       ├── intro.mp3
│       └── intro.ogg
├── parte-2-formulario-registro/
│   ├── registro.html
│   └── img/
│       └── captura-01.png
├── .gitignore
└── README.md
```

## Parte 1 — Página semántica
Página de portafolio personal que implementa `header`, `nav` (principal y
de pie de página, cada uno con su `aria-label`), `main`, `section`
(sobre mí, proyectos, logros, multimedia y preguntas frecuentes),
`article` (un proyecto por artículo), `aside` y `footer`, con listas
`ul`/`ol`/`dl`, enlaces internos por ancla y externos con
`target="_blank"` y `rel="noopener noreferrer"`, imagen con `alt`
descriptivo, un bloque de multimedia (audio) con transcripción en
`details`/`summary`, una sección de preguntas frecuentes con
`details`/`summary` y `mark`, y meta tags de SEO (`description`,
`author`, `robots`). Ver `parte-1-pagina-semantica/`.

## Parte 2 — Formulario de registro
Formulario de registro universitario con más de 10 tipos de
input HTML5 (text, email, password, tel, url, date, number,
range, color, file, checkbox, radio, hidden, textarea, select)
agrupados en 4 fieldsets con `legend`, con validación nativa
(`required`, `pattern` + `title`, `min`/`max`, `minlength`/`maxlength`),
todos los labels vinculados por `for`/`id` y atributos de accesibilidad
(`aria-describedby`, `autocomplete`). Envía por `POST` a `/api/registro`
(endpoint ficticio: un error 404 al enviar es lo esperado).
Ver `parte-2-formulario-registro/`.

## Decisiones de diseño

### 1. Estructura semántica de "Logros y Certificaciones" (Parte 1)
Se eligió la **Opción B: lista `<ul>` sin `<article>` individual**.
Aplicando el criterio de la guía teórica —"¿tiene sentido por sí solo
fuera del sitio?"—, un logro aislado (por ejemplo, "Curso de Fundamentos
de Desarrollo Web, noviembre de 2025") no aporta contexto suficiente si
se redistribuye solo: su valor está en formar parte del conjunto que
describe la trayectoria del estudiante. Por eso se marca como ítem de una
lista y no como contenido autocontenido, a diferencia de los proyectos,
que sí tienen descripción, tecnologías y enlace propios.

### 2. Formato multimedia de la introducción personal (Parte 1)
Se eligió la **Opción B: audio (`<audio>` con fuentes mp3 y ogg) con
transcripción completa dentro de `<details>`/`<summary>`**. El contenido
de la introducción es puramente verbal (nombre, carrera e intereses), así
que el video no aporta información esencial adicional y sí exige un
archivo mucho más pesado y un `.vtt` sincronizado. Para cumplir el
principio "Perceptible" de WCAG, la transcripción literal reemplaza a los
subtítulos (que `<audio>` no admite con `<track>`), y al estar en
`<details>` no satura la página pero queda disponible para cualquier
usuario y para lectores de pantalla.

### 3. Marcado del campo opcional "teléfono" (Parte 2)
Se eligió la **Opción A: texto "(opcional)" visible en el `<label>`**.
Es la alternativa más simple y robusta: el dato es evidente para todos
los usuarios y forma parte del nombre accesible del campo, sin depender
de que el navegador o lector de pantalla exponga la relación
`aria-describedby`, que en este formulario se reserva para ayudas de
formato (correo, contraseña, foto, biografía).

## Cómo visualizar el proyecto
1. Clonar el repositorio: `git clone <URL-del-repo>`
2. Abrir la carpeta en Visual Studio Code
3. Clic derecho en `parte-1-pagina-semantica/index.html` o
   `parte-2-formulario-registro/registro.html` → "Open with Live Server"

## Validación
- Parte 1: validar `index.html` en https://validator.w3.org/ (pestaña
  "Validate by File Upload").
- Parte 2: enviar el formulario vacío, con email sin `@`, con contraseña
  débil y con código de estudiante con letras para ver los mensajes de
  validación nativos del navegador.

## Capturas de pantalla
![Página principal](parte-1-pagina-semantica/img/captura-01.png)
![Formulario completo](parte-2-formulario-registro/img/captura-01.png)
