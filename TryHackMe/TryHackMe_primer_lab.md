# TryHackMe: Mi Primer Room

**Fecha:** 28 de Julio de 2026
**Tema Principal:** Descubrimiento de directorios ocultos (Web Enumeration / Fuzzing).

## Conceptos Aprendidos

En este laboratorio aprendí sobre el **Directory Brute-forcing** (Fuerza bruta de directorios). 
Muchos sitios web tienen páginas o directorios que no están enlazados públicamente (como paneles de administrador, respaldos de bases de datos, etc.). Aunque no haya un botón que te lleve ahí, las páginas existen en el servidor.

Para encontrar estas páginas ocultas, utilizamos técnicas de fuerza bruta o *fuzzing*.

## Herramientas Utilizadas

### Dirb
`dirb` es una herramienta de escaneo web que busca directorios y archivos ocultos en un servidor web lanzando peticiones HTTP basándose en un diccionario de palabras comunes.

**Comando básico:**
```bash
dirb http://url_objetivo.com
```

**¿Cómo funciona?**
La herramienta toma un archivo de texto lleno de palabras (un diccionario o *wordlist*) y prueba cada palabra detrás de la URL principal (ej. `url.com/admin`, `url.com/login`, `url.com/backup`). Si el servidor responde con un código de estado válido (como 200 OK), `dirb` nos avisa que esa página existe.

## Perspectiva Blue Team (Defensa)
Aunque `dirb` es una herramienta ofensiva (usada por atacantes y pentesters), como Blue Teamer es vital conocerla porque:
1. Nos ayuda a auditar nuestros propios sitios para asegurarnos de no dejar paneles de control expuestos.
2. En un SOC (Security Operations Center), si vemos miles de peticiones HTTP en pocos segundos hacia nuestro servidor web buscando rutas como `/admin`, `/test`, `/config`, sabremos identificar que estamos bajo un escaneo de directorios automatizado.
## Funcion de probador de penetracion
La funcion principal de estos es comprobar cuan seguros es el sistema y el osftware de una empresa checando que tan segur aes esta
buscar vulnerabilades y luego verificar si estas pueden ser explotadas, igual que haria un hacker real pero de forma controlada. todo se realiza bajo un acuerdo entre la empresa y el pentester, este proceso se llama engagement
## Un dia tipoco como tester de penetracion implica
1. Probar la seguridad de sistemas informaticos, redes y sitios webs
2. Realizar evaluaciones de seguridad, Auditorias y Analizar politicas de seguridad 
3. Asesorar a una organizacion sobre como evitar ataques o como prevenirlos 
