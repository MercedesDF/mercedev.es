#mercedev.es

Biblioteca profesional viva: código + documentación del proceso (La web publicada es el resultado; este repositorio es la fuente de verdad.

#Estructura

'/src' código fuente
'/public' salida lista para publicar
'/docs' decisiones, diagramas, glosario y errores resueltos
'/scripts' automatizaciones (p.ej. optimización de imágenes)
'/assets/originals' originales sin optimizar (ignorado por git)

#Principios

Mobile first + responsive
Accesibilidad (Lighthouse / axe-core)
JS mínimo (ESModules si se usa)
Seguridad: secretos en '.env' y fuera del repo
