# 🧠 Code2Text

**Convierte cualquier proyecto comprimido en un único archivo de texto optimizado para LLMs.**

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-blue?logo=github)](https://svn11x.github.io/conversor_code/)

---

## 📖 Descripción

**Code2Text** es una herramienta web que toma un archivo `.zip` con el código fuente de tu proyecto y genera un archivo `.txt` consolidado con:

- Una **estructura de árbol** del proyecto.
- El contenido de **todos los archivos de texto** (código, configuración, documentación), limpio de comentarios innecesarios.
- Un formato especial pensado para ser pegado directamente en asistentes de IA como ChatGPT, Claude, Gemini, etc.

Ideal para compartir el contexto completo de un proyecto con un modelo de lenguaje sin tener que copiar y pegar archivo por archivo.

## ✨ Características

- ✅ **Detección automática de archivos de texto**: no importa la extensión, si es texto legible se incluye. Los binarios se omiten del contenido (pero aparecen en el árbol).
- 🌳 **Árbol jerárquico visual** de toda la estructura del ZIP.
- 🧹 **Limpieza inteligente de comentarios** para Python, C/C++, JavaScript, XML, YAML, etc. (conserva shebangs).
- 🔍 **Buscador integrado** para filtrar archivos dentro del ZIP antes de procesar.
- 🎨 **Interfaz oscura moderna** con soporte para arrastrar y soltar archivos.
- 📦 **Funciona 100% en el navegador** (no se suben datos a ningún servidor).
- 🚀 **Listo para GitHub Pages**: solo necesitas alojar el HTML.

## 🖥️ Demo en vivo

Puedes probar la herramienta directamente desde GitHub Pages:

👉 **[https://tuusuario.github.io/code2text](https://tuusuario.github.io/code2text)**  

*(Reemplaza `tuusuario` por tu nombre de usuario de GitHub)*

## 📥 Cómo usar

1. **Abre la página** de Code2Text (localmente o desde GitHub Pages).
2. **Arrastra o selecciona** un archivo `.zip` que contenga tu proyecto.
3. (Opcional) Usa el buscador para filtrar los archivos que se incluirán.
4. Haz clic en **"Procesar y descargar"**.
5. Se generará un archivo `code2text_nombre-del-zip_fecha.txt` con el siguiente formato:

```
<estructura_proyecto>
src/
├── main.py
├── utils/
│   └── helpers.py
└── config.yaml
</estructura_proyecto>

<documentos_codigo>
  <archivo ruta="src/main.py" tipo=".py">
    # contenido limpio de main.py
  </archivo>
  <archivo ruta="src/utils/helpers.py" tipo=".py">
    # contenido de helpers.py
  </archivo>
  ...
</documentos_codigo>
```

¡Listo! Ya puedes copiar el contenido de ese `.txt` y pegarlo en tu LLM favorito.

## 🔧 Tecnologías utilizadas

- **HTML5 + CSS3** (diseño responsive, tema oscuro).
- **JavaScript (ES6+)** – Lógica de procesamiento de ZIP y detección de texto.
- **[JSZip](https://stuk.github.io/jszip/)** – Lectura de archivos comprimidos en el navegador.
- **GitHub Pages** – Despliegue estático sin backend.

## 🗂️ Estructura del proyecto

```
code2text/
├── index.html          # Archivo principal (autocontenido)
└── README.md           # Este archivo
```

## ⚙️ Cómo desplegar en GitHub Pages

1. Haz un fork de este repositorio o crea uno nuevo con el contenido.
2. Ve a **Settings > Pages**.
3. En *Source*, selecciona `main` (o `master`) y la carpeta `/ (root)`.
4. Haz clic en **Save**.
5. En unos segundos, tu sitio estará disponible en `https://tuusuario.github.io/code2text`.

## 🧪 Limitaciones conocidas

- Los archivos binarios grandes (>100 MB) pueden ralentizar el análisis inicial (pero no se incluirán en el resultado final).
- La limpieza de comentarios es básica; no maneja casos extremos como comentarios anidados en algunos lenguajes.
- No se conserva la estructura de directorios vacíos (solo se muestran los que contienen archivos).

¿Quieres que genere también un archivo `LICENSE` con el texto de MIT?
