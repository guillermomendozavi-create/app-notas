# Auditoría y Rediseño de UX/UI - App Notas

## 1. Tabla de Evaluación Heurística (Nielsen)

| Heurística | Problema Encontrado (Original) | Solución Aplicada (Rediseño) | Gravedad |
| :--- | :--- | :--- | :--- |
| **Visibilidad del estado** | Al agregar una nota o borrar datos no aparecía ningún mensaje ni confirmación. | Se agregó un contenedor con `role="status"` que muestra alertas como "Nota agregada" o "Nota eliminada". | Alta |
| **Coincidencia con el mundo real** | El botón decía "ok" y los enlaces usaban texto en mayúsculas sin contexto claro. | Se cambió a términos claros como "Agregar nota" y se estructuró un lenguaje directo. | Media |
| **Control y libertad** | Al presionar "BORRAR TODO" se eliminaban las notas al instante sin poder cancelar o deshacer. | Se implementó un cuadro de confirmación y la opción/función para revertir la acción. | Alta |
| **Prevención de errores** | Se podían agregar notas vacías o con espacios en blanco al presionar el botón "ok". | Se desactivó el botón mientras el campo esté vacío o se validó que contenga texto válido. | Alta |
| **Reconocer antes que recordar** | El campo dependía de un `placeholder="Nota"` que desaparecía al escribir. | Se implementó la etiqueta `<label>` visible vinculada mediante el atributo `for`. | Media |

---

## 2. Aplicación de Leyes de Usabilidad

* **Ley de Fitts:** Los botones de acción principal tienen una altura mínima de `44px` y un área táctil amplia, facilitando el clic/tap rápido.
* **Ley de Hick:** Las opciones de categoría se organizaron mediante `<optgroup>` por bloques lógicos para reducir el tiempo de decisión.
* **Ley de Miller:** La información y los elementos del formulario se agruparon en bloques temáticos, reduciendo la carga cognitiva.

---

## 3. Criterios de Accesibilidad y Principios Visuales

* **Etiquetas y Roles:** Cada elemento interactivo incluye `<label>` y atributos accesibles (`alt`, `role="status"`).
* **Foco Visible:** Se reemplazó `outline: none` por `:focus-visible` con un borde visual claro (`3px solid #f59e0b`).
* **Contraste y Paleta:** Variables definidas en `:root` asegurando un contraste superior a 4.5:1 (con escala superior a 14:1 en texto principal).

---

## 4. Resultados de Lighthouse (Accesibilidad)

| Métrica | Antes del Rediseño | Después del Rediseño |
| :--- | :---: | :---: |
| **Puntaje de Accesibilidad** | < 80 | **90+** |

### Capturas
* **Lighthouse Antes:** `docs/img/lighthouse-antes.png`
* **Lighthouse Después:** `docs/img/lighthouse-despues.png`