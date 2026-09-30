# Mis Notas de Clase: Git y GitHub

## 1. Comandos de la Terminal (Navegación)
Son los comandos de la línea de comandos para moverte entre carpetas antes de usar Git:

- `mkdir <nombre_carpeta>` — Crea una nueva carpeta.
- `cd <nombre_carpeta>` — Entra a una carpeta.
- `cd ..` — Sale de la carpeta actual (regresa un nivel arriba).
- `Cmd + J` (en Mac) / `Ctrl + J` (en Windows) — Abre o cierra la terminal en Visual Studio Code.

---

## 2. Configuración e Inicio de Git
- `git init` — Inicializa un repositorio de Git en la carpeta actual.
- `git clone <url_del_repositorio>` — Descarga una copia de un repositorio remoto de GitHub a tu computadora.
- `git status` — Muestra el estado de tu repositorio (archivos modificados, archivos listos para guardar y en qué rama estás).
- `git help` — Muestra la ayuda general o la lista de comandos de Git.

---

## 3. El Flujo Principal para Guardar y Subir Cambios
Un **commit** es como un **punto de control o foto de referencia** en la historia de tu proyecto. El flujo completo siempre lleva 3 pasos:

1. `git add .` — Prepara **todos** los archivos modificados/nuevos para el commit (o `git add <nombre_archivo>` si solo quieres preparar uno).
2. `git commit -m "mensaje descriptivo"` — Crea el punto de guardado local con un mensaje que explica qué cambios hiciste.
3. `git push` — Sube tus commits locales al repositorio remoto en GitHub.

---

## 4. Manejo de Ramas (Branches)
Las ramas sirven para trabajar en diferentes versiones del código sin romper la versión principal:

- **`main` / `master` (Producción):** Es la rama principal. Aquí va el código estable que ya funciona perfectamente.
- **`develop` / `dev` (Desarrollo/Pruebas):** Es la rama donde se hacen pruebas e integraciones antes de pasar a producción.

### Comandos para manejar ramas:
- `git branch` — Lista todas las ramas locales e indica en cuál estás parada actualmente.
- `git checkout -b <nombre_rama>` — **Crea** una nueva rama y se cambia automáticamente a ella.
- `git checkout <nombre_rama>` — **Cambia** a una rama existente.