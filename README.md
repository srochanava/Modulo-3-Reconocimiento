# Módulo 3 - Reconocimiento (OSINT y Footprinting)

Este repositorio documenta las actividades realizadas en el **Módulo 3: Reconocimiento** del curso "Hacking Ético - ARACT", enfocadas en técnicas de inteligencia de fuentes abiertas (OSINT), Google Dorks, Google Hacking Database (GHDB) y mapeo visual de infraestructura con Maltego.

**Objetivo general:**  
Demostrar cómo la información pública puede exponerse involuntariamente y cómo se puede recolectar de forma pasiva para mapear la superficie de ataque de un objetivo (sin interacción activa).

## Contenido del repositorio

- `evidencias.pdf` → Documento principal con las partes del ejercicio:
  - Parte 1: 8 búsquedas con Google Dorks + análisis de riesgos
  - Parte 2: Investigación en Exploit Database (GHDB) – 3 dorks 
  - Parte 3: Mapa visual generado en Maltego (captura del grafo)
  - Parte 4: Reflexión escrita (1 hoja)
- `capturas/` → Carpeta con todas las imágenes de evidencia:
  - Capturas de resultados de cada Google Dork
  - Capturas de la página de Exploit-DB con los dorks seleccionados
  - Captura del grafo final en Maltego

## Parte 1 – Google Dorks (Búsquedas avanzadas)

Se realizaron **8 búsquedas** utilizando los operadores solicitados:

| # | Dork utilizado                                      | Tipo de exposición detectada                  | Riesgo |
|---|-----------------------------------------------------|-----------------------------------------------|--------|
| 1 | `site:example.com filetype:pdf`                     | Archivos PDF en dominio de prueba             | Bajo   |
| 2 | `inurl:admin "login"`                               | Paneles de administración expuestos          | Alto   |
| 3 | `intitle:"index of" -site:example.com`              | Directorios abiertos (index of)               | Alto   |
| 4 | `"confidential document" filetype:doc OR filetype:docx` | Documentos confidenciales en formatos Office | Medio-Alto |
| 5 | `site:gov filetype:xls -site:irs.gov`               | Hojas de cálculo gubernamentales              | Medio  |
| 6 | `inurl:backup filetype:sql`                         | Backups de bases de datos SQL                 | Alto   |
| 7 | `intitle:"database" "username" "password"`          | Referencias a credenciales de bases de datos  | Alto   |
| 8 | `site:edu inurl:login OR inurl:portal`              | Portales de acceso en instituciones educativas| Medio-Alto |

**Conclusión de esta parte:** Muchas organizaciones exponen accidentalmente información sensible (logins, backups, documentos, directorios) que es indexada por motores de búsqueda.

## Parte 2 – Investigación en Google Hacking Database (GHDB)

Se consultó https://www.exploit-db.com/google-hacking-database y se analizaron 3 dorks representativos:

1. `site:github.com "BEGIN OPENSSH PRIVATE KEY"`  
   → Categoría: Files Containing Passwords  
   → Exposición: Claves privadas SSH expuestas en repositorios públicos

2. `inurl:home.htm intitle:1766`  
   → Categoría: Various Online Devices  
   → Exposición: Interfaces de dispositivos IoT o routers expuestos

3. `intext:"aws_access_key_id" | intext:"aws_secret_access_key" filetype:json | filetype:yaml`  
   → Categoría: Files Containing Passwords  
   → Exposición: Credenciales AWS en archivos de configuración

## Parte 3 – Maltego (Mapeo Visual de Infraestructura)

**Dominio utilizado:** `example.com` (dominio autorizado y seguro para pruebas)

**Flujo de transforms ejecutado:**
- Domain → DNS Names
- DNS Names → IP Addresses
- IP Addresses → Location (GeoIP)

**Resultado:** Grafo visual que muestra la relación entre el dominio, sus nombres DNS asociados, las direcciones IP y la geolocalización aproximada.

*(Captura incluida en `capturas/maltego_grafo.png` y en el PDF)*

## Parte 4 – Reflexión

Resumen de los puntos clave respondidos:

- **Reconocimiento pasivo vs activo**  
  Pasivo: solo fuentes públicas, sin tráfico al objetivo (Google, WHOIS, Shodan, etc.)  
  Activo: interacción directa (Nmap, escaneo de puertos, etc.) → detectable

- **Por qué sin autorización puede ser ilegal**  
  Puede violar leyes de protección de datos (RGPD, LFPDPPP México), considerarse preparación de delito informático o espionaje industrial.

- **Aprendizaje principal**  
  La mayor parte de las exposiciones provienen de configuraciones descuidadas (directorios abiertos, credenciales en GitHub, archivos indexados). La higiene digital y el control de lo que se publica/indexa es fundamental.

## Notas finales

- Todas las actividades se realizaron de forma **ética** y **pasiva**, utilizando únicamente dominios públicos o de prueba.
- No se realizó ningún escaneo activo ni interacción directa con sistemas reales.
- Fecha de realización: Marzo 2026
