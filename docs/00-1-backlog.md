PROYECTO mercedev.es con SCRUM
0) Marco Scrum operativo
Roles (tú misma, pero con sombreros)
Product Owner (PO): decides prioridades (empleabilidad, coherencia de marca).


Scrum Master (SM): proteges foco, limitas WIP, facilitas cadencia.


Dev: implementas.


Cadencia recomendada
Sprints de 1 semana (o 2 si te conviene).


Planning: 30–45 min.


Daily (auto): 5 min con 3 preguntas: qué hice / qué haré / bloqueo.


Review: 20 min (demo en web + repo).


Retro: 15 min (qué mantengo, qué corto, qué pruebo).


Definición de Done (DoD) global
Para cada entrega:
✅ funcional en móvil y desktop (mobile-first)


✅ accesible (mínimo: alt/aria, navegación teclado; ideal: Lighthouse/Axe)


✅ sin secretos en repo (.env fuera)


✅ errores manejados (al menos “happy path” + fallos previsibles)


✅ documentado en /docs (decisión + cómo se hizo)


✅ README actualizado si cambia estructura o ejecución



1) Epic: Repo como “fuente de verdad” (Base)
Checkpoint 1.1 — Repo creado y publicado
Entregables
Repo mercedev.es en GitHub


Estructura base:


/src, /public, /docs, /scripts, /.github/workflows


.gitignore con seguridad


README.md inicial


/docs/00-intencion.md (ya lo tienes)


DoD
Primer commit limpio y push a main


README explica “web resultado / repo fuente de verdad”



2) Epic: Documentación mínima que desbloquea construcción (Antes de código)
Checkpoint 2.1 — Mapa exacto de la web
Entregable
/docs/01-mapa-web.md con:


secciones: Home, Sobre mí, Cuaderno de Bitácora, Laboratorio, Mercí (proyecto), No-tienda, Contacto


qué entra / qué NO entra en cada sección


Checkpoint 2.2 — Biblioteca conceptual (semántica)
Entregable
/docs/02-biblioteca.md:


estanterías: Obra civil (base) → seguridad/procesos → web/experimentos → curiosidades colaterales


reglas: color = categoría, “libro” = post/proyecto/nota


Checkpoint 2.3 — Mercí v0 (contrato de comportamiento)
Entregable
/docs/03-merci-v0.md:


qué observa / qué no


cuándo interviene / cuándo calla


tono (sobrio, irónico leve, no infantil)


DoD de Epic 2
Con estos 3 docs, ya no hay decisiones abiertas para empezar la web.



3) Epic: Web v1 “funcional” (sin perfeccionismo)
Objetivo: publicar rápido una versión simple, coherente y extensible.
Checkpoint 3.1 — Wireframe textual + arquitectura de navegación
Entregables
/docs/04-home-estructura.md con el recorrido:


Biblioteca (marco)


Obra civil (base)


Evolución: Agile + ciber + S&S + web


Art de Coté (creación colateral)


Cuaderno de Bitácora (libros nuevos)


Laboratorio (experimentos)


Mercí (sutil)


No-tienda (identidad lateral)


Menú final y enlaces internos


Checkpoint 3.2 — Implementación estática mínima (HTML/CSS)
Entregables
Home + 5 páginas vacías pero estructuradas (con contenido mínimo real):


/sobre-mi/, /Cuaderno de Bitácora/, /laboratorio/, /merci/, /no-tienda/, /contacto/


Estilos base (mobile-first), tipografía, espaciado


Accesibilidad básica (aria, focus, contraste)


Checkpoint 3.3 — “Biblioteca” como componente visual v1
Entregables
Biblioteca en hero y separadores (imagen o SVG, pero coherente)


Semántica alineada con estanterías (aunque sea “placeholder”)


DoD de Epic 3
Sitio navegable, legible y coherente.


Lighthouse sin “rojos” graves en Performance/Accessibility.



4) Epic: Publicación y “doble espejo” (DO + GitHub Pages)
Checkpoint 4.1 — WordPress en DigitalOcean como capa de publicación
Estrategia
No escribir “la verdad” en WordPress: WordPress solo sirve el resultado.


Entregable
mercedev.es sirve la v1 (aunque sea simple)


Checkpoint 4.2 — GitHub Pages como espejo técnico
Entregable
Deploy automático a GitHub Pages desde main (o gh-pages)


URL espejo visible en README (para demo técnica)


Checkpoint 4.3 — GitHub Actions v1
Entregable
Workflow básico:


build (si aplica) / copia a public


deploy a Pages


opcional: check HTML (lint) + accesibilidad básica


DoD de Epic 4
Cada push a main actualiza el espejo.


Publicación principal estable.



5) Epic: Cuaderno de Bitácora v1 (contenido y sistema, no “solo posts”)
Checkpoint 5.1 — Modelo de post (plantilla)
Entregables
/docs/05-Cuaderno de Bitácora-template.md con estructura:


problema → decisión → implementación → errores → aprendizajes → siguiente iteración


Taxonomía mínima (tags):


obra-civil, agile, ciberseguridad, seguridad-salud, web, colateral, merci


Checkpoint 5.2 — Publicar 5 posts iniciales (semilla)
Entregables
5 entradas cortas pero potentes (200–600 palabras), p.ej.:


“Crear de forma colateral: lo que en obra se aprende a fuego”


“Iterar no es repetir: es recolocar”


“Documentar es prevención (PRL ↔ ciber)”


“Biblioteca viva: cómo organizo conocimiento”


“Mercí v0: qué observa y por qué”


Checkpoint 5.3 — Autopublicación a LinkedIn (v1)
Opciones (elige una por simplicidad)
RSS del Cuaderno de Bitácora → herramienta de automatización (Make/Zapier/IFTTT) → LinkedIn post


GitHub Actions → webhook → publicador (si lo quieres más técnico)


Entregable
Cada nuevo post genera automáticamente:


título + extracto breve + enlace


DoD de Epic 5
Cuaderno de Bitácora vivo, consistente con Art de Coté.


LinkedIn amplifica sin esfuerzo manual.



6) Epic: Mercí en la web (mascota simbólica, “en la nube”)
Checkpoint 6.1 — Mercí SVG “canónica”
Entregables
assets/merci/merci.svg (🔥 + </> + !!, tu estilo)


Guía breve: tamaños, posiciones, “nube”


Checkpoint 6.2 — Interacciones mínimas (sin IA)
Entregables
Mercí aparece en puntos concretos:


Home (muy sutil)


Cuaderno de Bitácora (nota al margen ocasional)


Laboratorio (más presente)


No-tienda (protagonista relativo)


Tooltip/mini panel con 1 frase contextual (no chat)


Checkpoint 6.3 — Página “Mercí (proyecto)”
Entregables
Explicas la idea: “conciencia ligera del sistema”


Roadmap público de Mercí (v1 foco, v2 info, v3 tiempo)


DoD de Epic 6
Mercí aporta identidad sin infantilizar.


No interrumpe UX.



7) Epic: “No-tienda” de Mercí (merch sin e-commerce duro)
Checkpoint 7.1 — Concepto y catálogo mínimo
Entregables
Página con 6–12 ítems tipo “archivo curioso”:


póster, pegatina, camiseta (conceptual)


Sin compra directa (o con “lista de interés”)


Checkpoint 7.2 — Integración narrativa
Entregables
Cada item tiene:


microhistoria (Art de Coté: de descarte → recomposición)


frase técnica con ironía sobria


DoD de Epic 7
“No-tienda” suma marca, no distrae.



8) Epic: Laboratorio (proyectos y trazabilidad)
Checkpoint 8.1 — Plantilla de proyecto
Entregables
/docs/06-proyecto-template.md:


objetivo, alcance, no-alcance


riesgos, seguridad, UX


decisiones, iteraciones


checklist DoD por proyecto


Checkpoint 8.2 — Primer proyecto: Mercí Focus (v1)
Entregables
Documento y backlog del proyecto Mercí Focus:


métricas de dispersión (cambios de ventana, tiempo por app, etc.)


privacidad: no contenido, solo señales


Prototipo mínimo (aunque sea offline/desktop primero)


DoD de Epic 8
Laboratorio no es “galería”: es sistema de trabajo.



Backlog inicial sugerido (orden realista)
Repo (1.1)


Mapa web (2.1)


Biblioteca conceptual (2.2)


Mercí v0 (2.3)


Web v1 navegable (3.2)


Biblioteca visual v1 (3.3)


Publicación DO + Pages (4.1–4.3)


Cuaderno de Bitácora template + 5 posts (5.1–5.2)


Autopost LinkedIn (5.3)


Mercí SVG + microinteracciones (6.1–6.2)


No-tienda v1 (7.1)


Laboratorio + Mercí Focus (8.1–8.2)



Checkpoints “de control” (anti-dispersión)
Cada fin de sprint, preguntas fijas:
¿La web está más publicable que hace 7 días?


¿Hay una decisión nueva documentada en /docs?


¿He reducido trabajo duplicado?


¿Qué debo no hacer la semana que viene?


