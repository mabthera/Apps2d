# Instrucciones para añadir el footer de autor y licencia

Este documento explica cómo insertar el mismo footer en cualquier archivo HTML del proyecto.

## 1. Añadir los estilos CSS

Pega este bloque dentro de la etiqueta `<style>` del archivo HTML. Si no existe, añádelo dentro de `<head>`.

```css
.app-footer {
  display: grid;
  gap: 12px;
  justify-items: center;
  text-align: center;
  margin-top: 18px;
  padding: 4px 18px 10px;
  color: var(--muted);
  font-family: "Segoe UI", Arial, sans-serif;
}

.footer-meta {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  flex-wrap: nowrap;
  font-size: 0.94rem;
  line-height: 1.55;
  white-space: nowrap;
}

.footer-separator {
  color: rgba(88, 101, 106, 0.55);
  font-weight: 700;
}

.footer-highlight {
  display: inline-block;
  font-weight: 800;
  color: var(--ink);
  background: rgba(28, 77, 127, 0.1);
  border-radius: 999px;
  padding: 2px 10px;
  text-decoration: none;
}

a.footer-highlight:hover,
a.footer-highlight:focus-visible {
  background: rgba(28, 77, 127, 0.16);
  outline: none;
}

.license-subtitle {
  max-width: 48ch;
  font-size: 0.9rem;
  line-height: 1.5;
}
```

## 2. Añadir el ajuste responsive

Dentro del `@media` principal del documento, añade esta línea:

```css
.footer-meta { flex-wrap: wrap; white-space: normal; }
```

Si el archivo no tiene ningún `@media`, puedes crear uno como este:

```css
@media (max-width: 980px) {
  .footer-meta { flex-wrap: wrap; white-space: normal; }
}
```

## 3. Insertar el HTML del footer

Pega este bloque justo antes de `</main>`. Si el archivo no usa `<main>`, colócalo antes de `</body>`.

```html
<footer class="app-footer" aria-label="Créditos">
  <div class="footer-meta">
    <span>Creado por:</span>
    <span class="footer-highlight">David Rodríguez Vicente</span>
    <span class="footer-separator">|</span>
    <span>Licencia:</span>
    <a class="footer-highlight" href="https://creativecommons.org/licenses/by-nc-sa/4.0/" target="_blank" rel="noopener noreferrer">CC BY-NC-SA 4.0</a>
  </div>
  <div class="license-subtitle">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International</div>
</footer>
```

## 4. Comprobaciones recomendadas

1. Verifica que el documento use `<meta charset="UTF-8">` para mostrar bien tildes y caracteres especiales.
2. Comprueba que existan las variables CSS `var(--muted)` y `var(--ink)`.
3. Si el archivo no usa esas variables, sustitúyelas por colores directos, por ejemplo:

```css
color: #5b6675;
color: #1f2937;
```

## 5. Resumen rápido

1. Copiar el CSS del footer.
2. Añadir la regla responsive para `.footer-meta`.
3. Pegar el bloque `<footer ...>` al final del contenido.
4. Revisar en navegador que el texto y el enlace se ven correctamente.
