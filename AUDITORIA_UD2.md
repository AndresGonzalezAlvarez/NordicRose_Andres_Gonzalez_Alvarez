# AUDITORÍA UD2 - Buenas Prácticas HTML/CSS

## Checklist

| Criterio | Estado | Evidencia |
|---------|--------|-----------|
| **HTML semántico real** (header/nav/main/section/article/footer) | ✅ | `index.html`: header (línea 10), nav (línea 12), main (línea 20), section (líneas 22, 30), article (línea 33+), footer (línea 96)<br>`article.html`: header (línea 10), nav (línea 12), main (línea 20), section (múltiples), article (línea 21), footer (línea 149) |
| **alt en todas las imágenes** | ✅ | Todas las imágenes tienen atributo `alt` con descripciones:<br>`index.html`: líneas 11, 21, 34, 39, 44, 49, 54, 59, 64, 69, 74, 79, 84, 89, 97<br>`article.html`: líneas 11, 27, 29, 41, 86, 97, 102, 107, 112, 117, 122, 127, 150 |
| **Nada de estilos inline ni `<style>` en HTML** | ✅ | No se encontraron `style=` ni etiquetas `<style>` en ningún archivo HTML |
| **Clases en inglés kebab-case** (no IDs para CSS) | ✅ | Todas las clases usan kebab-case: `site-header`, `main-nav`, `article-card`, `read-next-grid`, etc.<br>Los IDs existentes (`newsletter-email`, `about`, `links`, `projects`) son para funcionalidad, no para CSS |
| **Layout con Flexbox** (header/nav) | ✅ | `css/style.css` líneas 58, 75: `.site-header` y `.main-nav` usan `display: flex` |
| **Layout con Grid** (listados) | ✅ | `css/style.css` líneas 181, 392, 767: `.articles-grid` y `.read-next-grid` usan `display: grid` |
| **Media queries para móvil** | ✅ | `css/style.css`: `@media (max-width: 768px)` (líneas 215, 925, 1378) y `@media (min-width: 900px)` (líneas 315, 661, 878) |
| **CSS ordenado** (:root, reset básico, estructura por bloques) | ✅ | `css/style.css`: `:root` con variables (líneas 1-25), reset básico (líneas 27-54), estructura por bloques comentados (Header, Main Content, Articles Section, Footer, Article Page Styles, etc.) |

## Lista de Cambios Mínimos (máx 8)

### 1. ⚠️ **index.html línea 13**: Enlace `#blog` sin destino
   - **Problema**: `<a href="#blog">` no tiene sección con `id="blog"`
   - **Solución**: Cambiar a `href="index.html"` o añadir `<section id="blog"></section>` al final del main

### 2. ⚠️ **index.html línea 27**: `<div class="divider">` podría ser más semántico
   - **Problema**: Usa `<div>` en lugar de elemento semántico
   - **Solución**: Cambiar a `<hr class="divider">` (opcional, no crítico)

### 3. ✅ **CSS duplicado**: `.article-card-image` y `.article-card-title` duplicados
   - **Problema**: `css/style.css` líneas 196-212 y 278-294 tienen estilos duplicados
   - **Solución**: Eliminar duplicados (líneas 278-294)

### 4. ✅ **CSS orden**: Algunos estilos de article-page podrían estar mejor agrupados
   - **Estado**: Aceptable, pero podría mejorarse la organización
   - **Solución**: (Opcional) Reorganizar bloques de `.article-page` juntos

### 5. ✅ **index.html**: Falta `id="blog"` para el enlace de navegación
   - **Solución**: Añadir `<section id="blog"></section>` al final del main (similar a article.html)

### 6. ✅ **article.html**: Secciones vacías con id (líneas 144-146)
   - **Estado**: Correcto para resolver warnings, pero podrían tener contenido mínimo
   - **Solución**: (Opcional) Añadir contenido placeholder o mantener vacías

### 7. ✅ **CSS**: Variables `:root` bien definidas
   - **Estado**: ✅ Correcto

### 8. ✅ **HTML**: Estructura semántica completa
   - **Estado**: ✅ Correcto

---

## Cambios Críticos a Aplicar

### Cambio 1: Añadir `id="blog"` en index.html
**Archivo**: `index.html`  
**Línea**: ~94 (antes del `</main>`)  
**Acción**: Añadir `<section id="blog"></section>` o cambiar `href="#blog"` a `href="index.html"`

### Cambio 2: Eliminar CSS duplicado
**Archivo**: `css/style.css`  
**Líneas**: 278-294  
**Acción**: Eliminar estilos duplicados de `.article-card-image` y `.article-card-title`

