# Módulo 3 - Reconocimiento

Este repositorio documenta las actividades realizadas en el **Módulo 3: Reconocimiento** del curso **"Hacking Ético - Impartido por ARACT"**, enfocadas en técnicas de inteligencia de fuentes abiertas (OSINT), Google Dorks, Google Hacking Database (GHDB) y mapeo visual de infraestructura con Maltego.

**Objetivo general:**  
Demostrar cómo la información pública puede exponerse involuntariamente y cómo se puede recolectar de forma pasiva para mapear la superficie de ataque de un objetivo (sin interacción activa).

## Contenido del repositorio

- `evidencias.pdf` → Documento principal con las partes del ejercicio:
  - Parte 1: 8 búsquedas con Google Dorks + análisis de riesgos
    →  Capturas de resultados de cada Google Dork
  - Parte 2: Investigación en Exploit Database (GHDB) – 3 dorks
    →  Capturas de la página de Exploit-DB con los dorks seleccionados
  - Parte 3: Mapa visual generado en Maltego (captura del grafo)
  - Parte 4: Reflexión escrita
- `capturas/` → Carpeta con imágenes de evidencia: 
  - Captura del grafo final en Maltego


**RESUMEN:** 

## Reconocimiento pasivo y activo:
El reconocimiento pasivo recopila información pública sin interactuar directamente con el objetivo (ej. Google Dorks, WHOIS, Shodan), evitando detección. 
El activo implica interacción directa (ej. escaneo de puertos con Nmap), generando tráfico que puede ser detectado, aumentando riesgos éticos y legales.

En el contexto de OSINT ético (y especialmente en certificaciones, cursos y checklists profesionales como los de SANS, OSINT Curious, Trace Labs, Bellingcat con enfoque ético, o guías de buenas prácticas en ciberseguridad), lo primero y obligatorio antes de iniciar cualquier investigación que pueda afectar a personas o entidades reales es:
Obtener autorización explícita (consentimiento informado o permiso escrito) del cliente, la organización objetivo o la entidad que solicita la investigación.

Sin autorización explícita, muchas acciones de OSINT (incluso las pasivas) pueden cruzar líneas éticas o legales:

- Recolección de datos personales sin base legítima, Posible violación de privacidad. Riesgo de mal uso de la información.

- **Aprendizaje principal**  
  La mayor parte de las exposiciones provienen de configuraciones descuidadas (directorios abiertos, credenciales en GitHub, archivos indexados). La higiene digital y el control de lo que se publica/indexa es fundamental.

## Notas finales

- Todas las actividades se realizaron de forma **ética** y **pasiva**, utilizando únicamente información propia en dominios públicos o de prueba.
- No se realizó ningún escaneo activo ni interacción directa con sistemas reales.
- Fecha de realización: Marzo 2026
