# 02-biblioteca.md · Semántica y Sistema Visual

**Estatus:** Definición de diseño (Bloqueante para Epic 3)
**Concepto:** La web no es un feed; es una estantería técnica viva.

---

## 1. La Metáfora (El Mueble)
La interfaz imita una estantería de clasificación industrial.
- **Orden:** De lo más denso/físico (abajo) a lo más etéreo/experimental (arriba).
- **Espacio Negativo:** Los huecos son tan importantes como el contenido (aire, descanso visual).

## 2. Las Estanterías (Categorías Temáticas)
Cada nivel de la estantería corresponde a una disciplina técnica.

### 🏗️ Estante 1: Obra Civil (Base)
* **Concepto:** Cimientos, hormigón, estructuras físicas, "el mundo real".
* **Semántica:** Solidez, peso, inmutabilidad.
* **Código de Color:** `Gris Hormigón` / `Ocre Tierra`.
* **Uso:** Origen profesional, pensamiento estructural.

### 🛡️ Estante 2: Seguridad y Procesos (Estructura Lógica)
* **Concepto:** Normativa, prevención (PRL), ciberseguridad, hardening.
* **Semántica:** Protección, reglas, límites claros.
* **Código de Color:** `Azul Ingeniero` / `Acero`.
* **Uso:** Cómo se hacen las cosas para que no se rompan.

### 🧪 Estante 3: Laboratorio y Web (La Capa Viva)
* **Concepto:** Código, experimentos zsh, frontend, iteraciones rápidas.
* **Semántica:** Flexibilidad, prueba-error, crecimiento.
* **Código de Color:** `Verde Terminal` / `Lima`.
* **Uso:** El presente activo, lo que está "en construcción".

### 🎨 Estante 4: Art de Coté (Colateral)
* **Concepto:** Lo que sobra y se reaprovecha. La "No-tienda".
* **Semántica:** Curiosidad, ironía sobria, creatividad residual.
* **Código de Color:** `Acento Naranja` (Señalización).
* **Uso:** Identidad y marca personal.

## 3. Los Volúmenes (Tipos de Contenido)
La forma visual del elemento en la web indica la profundidad de lectura (DoD Visual).

| Objeto Visual | Tipo de Contenido | Profundidad | Dónde vive |
| :--- | :--- | :--- | :--- |
| **📕 Libro (Lomo ancho)** | Proyecto Documentado | +5 min lectura | Laboratorio / Docs |
| **📄 Folio / Nota** | Post Bitácora | 1-3 min lectura | Cuaderno de Bitácora |
| **📦 Caja** | Ítem Físico / Archivo | Visual / Objeto | No-tienda |
| **🐈‍⬛ Hueco (Mercí)** | Espacio / Silencio | N/A | Márgenes / Separadores |

## 4. Reglas de Comportamiento Visual
1. **Hover:** Al pasar el ratón por un libro, se ilumina toda su "estantería" (contexto).
2. **Navegación:** No hay menús dropdown infinitos; navegas por "pisos" (estantes).
3. **Tipografía:**
    - Estantería (Títulos): Sans-serif técnica, rotunda (ej. Inter, Roboto Mono).
    - Libros (Cuerpo): Serif legible para lectura prolongada (ej. Merriweather, Lora).

## 5. La Vista "Carpeta de Obra" (El Índice)
Si la Estantería es la vista "Exploración", la Carpeta es la vista "Gestión".

* **Diseño:** Lista limpia tipo sistema de archivos o índice de anillas con pestañas laterales.
* **Separadores (Tabs de plástico):**
    * 🟧 **Obra Civil:** Pestaña Ocre (Base).
    * 🟦 **Seguridad:** Pestaña Azul (Procesos).
    * 🟩 **Laboratorio:** Pestaña Verde (Web/Código).
    * 🟥 **Art de Coté:** Pestaña Naranja (Colateral/No-tienda).
    * ⬛ **Glosario:** Pestaña Negra (Mercí/Diccionario).

* **Comportamiento:** Al hacer click en una pestañita de plástico, se filtra la lista de contenidos.

## 6. Integración del Glosario
* **Micro-interacción:** Las palabras técnicas tendrán un subrayado punteado sutil (estilo `abbr`).

---
*Este documento bloquea el diseño CSS de la Epic 3.*