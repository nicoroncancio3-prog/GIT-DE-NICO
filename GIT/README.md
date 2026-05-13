### Notas de Git

Flujo rápido — cuando quieres trabajar de forma segura con un remoto
bash# 1. Traer cambios del remoto
git fetch origin

# 2. Ver qué cambió sin tocar tu rama local
git log --oneline --graph HEAD..origin/main
git diff HEAD..origin/main

# 3. Actualizar tu rama local
git checkout main
git merge --ff-only origin/main
# O con rebase: git rebase origin/main

# Equivalente directo con pull:
git pull --ff-only
Flujo para trabajar en una feature
bashgit switch -c feature/mi-feature                 # Crear y cambiar a una nueva rama
# ... trabajar, hacer commits ...
git fetch origin                                     # Traer cambios nuevos de main
git rebase origin/main                               # Actualizar la rama con los últimos cambios
git push -u origin feature/mi-feature                # Subir la rama para abrir un pull request
Flujo para recuperar algo borrado por error
bashgit reflog                                       # Ver el historial completo de movimientos
# Identificar el hash del estado que quieres recuperar
git reset --hard HEAD@{N}                            # Volver a ese estado (reemplaza N por el número del reflog)

 Áreas de Git — cómo Git organiza internamente tu trabajo

Working directory (directorio de trabajo): donde se encuentran los archivos del proyecto en el sistema de archivos.
Staging area (área de preparación): donde se colocan los archivos que se van a incluir en el próximo commit. Se agregan con git add.
Repository (repositorio): donde se almacenan todos los commits y la historia del proyecto. Se crean con git commit.

 Estados de los archivos — en qué punto del ciclo está cada archivo

Untracked (no rastreado): archivo que Git no está siguiendo. No está en staging ni en el repositorio.
Modified (modificado): archivo que fue cambiado pero aún no fue agregado al staging area.
Staged (preparado): archivo agregado al staging area, listo para el próximo commit.
Unmodified (sin modificar): archivo que no ha cambiado desde el último commit.


 Configuración — lo primero que debes hacer al instalar Git o en una máquina nueva
bashgit --version                                    # Verificar versión de Git

git config --global user.name "Tu Nombre"            # Configurar nombre de usuario
git config --global user.email "correo@gmail.com"    # Configurar correo

git config --system -l                               # Ver configuración del sistema
git config --global -l                               # Ver configuración global
git config --local -l                                # Ver configuración local del repositorio
git config --list                                    # Ver todas las configuraciones

# Si aparece "master" en vez de "main":
git config --global init.defaultBranch main
git config --system init.defaultBranch main

 Comandos básicos — para iniciar un proyecto o unirte a uno existente
bashgit init                                         # Inicializar un repositorio en el directorio actual
git clone [url]                                      # Clonar un repositorio remoto ya existente
git clone [url] --depth 1                            # Clonar solo el último commit (más rápido, útil en CI/CD)
git clone [url] --branch [rama]                      # Clonar y posicionarse directamente en una rama específica
git status                                           # Ver qué archivos cambiaron, están en staging o sin rastrear
git status -s                                        # Ver el estado en formato corto (una línea por archivo)

 Git add — seleccionar qué cambios incluirás en el próximo commit
bashgit add [archivo]                                # Agregar un archivo específico al staging area
git add .                                            # Agregar todos los archivos modificados del directorio actual
git add -p                                           # Modo interactivo: elegir hunk por hunk qué agregar (muy útil para commits limpios)

 Git commit — guardar una instantánea permanente de tu trabajo
bashgit commit -m "[mensaje]"                        # Crear un commit con mensaje
git commit -a -m "[mensaje]"                         # Hacer commit de todos los archivos modificados (salta el git add)
git commit --amend -m "[nuevo mensaje]"              # Corregir el mensaje del último commit (antes de hacer push)
git commit --amend                                   # Modificar el último commit (abre editor)
git commit --amend --no-edit                         # Agregar cambios al último commit sin cambiar el mensaje

 Git diff — ver exactamente qué líneas cambiaron y dónde
bashgit diff                                         # Cambios en working directory que aún no están en staging
git diff --staged                                    # Cambios que ya están en staging, listos para el commit
git diff [rama1] [rama2]                             # Comparar el estado completo de dos ramas
git diff [hash1] [hash2]                             # Ver qué cambió entre dos commits específicos

 Git log — explorar el historial de commits del proyecto
bashgit log                                          # Historial completo con hash, autor, fecha y mensaje
git log --oneline                                    # Historial resumido: una línea por commit
git log --graph                                      # Historial visual con ramas y merges
git log --all                                        # Incluye el historial de todas las ramas
git log --date-order                                 # Ordenar commits por fecha
git log --stat                                       # Ver qué archivos cambiaron y cuántas líneas
git log --oneline --date-order --all --graph         # Vista completa y visual (la más útil del día a día)
git log --author="[nombre]"                          # Filtrar commits por autor
git log --grep="[texto]"                             # Buscar commits cuyo mensaje contenga un texto
git log -n [numero]                                  # Ver solo los últimos N commits
git log -- [archivo]                                 # Ver el historial de cambios de un archivo específico

git show [hash]                                      # Ver los cambios exactos introducidos por un commit
git blame [archivo]                                  # Ver línea por línea quién hizo cada cambio y en qué commit

git shortlog                                         # Resumen de commits agrupados por autor
git shortlog -sn                                     # Ranking de autores por número de commits

 Deshacer cambios — revertir modificaciones antes o después del staging
bashgit restore [archivo]                            # Descartar cambios locales en un archivo (working directory)
git restore --staged [archivo]                       # Sacar un archivo del staging sin perder los cambios
git restore --staged .                               # Sacar todos los archivos del staging

git checkout -- [archivo]                            # Igual que restore (versión antigua, aún funciona)
git checkout [hash] -- [archivo]                     # Recuperar la versión de un archivo tal como estaba en un commit
 Git reset — mover el HEAD a un commit anterior, con distintos niveles de impacto

Úsalo para deshacer commits locales que aún no has subido al remoto.

bashgit reset [hash]                                 # Deshace commits, deja los cambios en staging (--mixed por defecto)
git reset --soft [hash]                              # Deshace commits, mantiene los cambios en staging listos para recomitear
git reset --mixed [hash]                             # Deshace commits, mueve los cambios al working directory
git reset --hard [hash]                              #  DESTRUCTIVO: deshace commits y borra todos los cambios permanentemente
 Git revert — deshacer un commit creando uno nuevo, sin reescribir el historial

La alternativa segura a reset cuando el commit ya está en el remoto o es compartido con el equipo.

bashgit revert [hash]                                # Crear un nuevo commit que deshace los cambios del commit indicado
git revert [hash] --no-commit                        # Preparar la reversión en staging sin hacer el commit todavía
git revert [hash1]..[hash2]                          # Revertir un rango de commits
git revert --abort                                   # Cancelar un revert en curso

 Git rm — eliminar archivos del repositorio o del staging sin borrarlos a mano
bashgit rm [archivo]                                 # Eliminar un archivo del disco y del repositorio
git rm --cached [archivo]                            # Dejar de rastrear un archivo sin borrarlo del disco (útil para .gitignore tardío)
git rm -r [directorio]                               # Eliminar un directorio completo del repositorio
git rm -r --cached [directorio]                      # Dejar de rastrear un directorio sin borrarlo del disco

 Git mv — renombrar o mover archivos y que Git lo registre correctamente

Equivale a hacer mv + git rm + git add, pero en un solo paso.

bashgit mv [archivo-original] [archivo-nuevo]        # Renombrar un archivo
git mv [directorio-original] [directorio-nuevo]      # Renombrar un directorio
git mv [archivo] [directorio]                        # Mover un archivo a otro directorio

 Git branch — gestionar las ramas del repositorio

Cada rama es una línea de desarrollo independiente. Úsalas para trabajar en features, fixes o experimentos sin afectar main.

bashgit branch                                       # Listar ramas locales
git branch -a                                        # Listar todas las ramas (locales y remotas)
git branch -r                                        # Listar solo ramas remotas
git branch [nombre]                                  # Crear una nueva rama (no cambia a ella)
git branch -d [nombre]                               # Eliminar una rama ya mergeada
git branch -D [nombre]                               # Forzar la eliminación aunque no esté mergeada
git branch -m [nombre-antiguo] [nombre-nuevo]        # Renombrar una rama local
git branch -M [nombre-nuevo]                         # Renombrar la rama actual forzando si el nombre ya existe
git branch -vv                                       # Ver el último commit y la rama remota vinculada de cada rama local

 Git checkout / switch — moverte entre ramas o commits
bash# Switch (versión moderna — recomendada para cambiar de rama)
git switch [rama]                                    # Cambiar a una rama existente
git switch -c [rama]                                 # Crear una rama nueva y cambiar a ella inmediatamente

# Checkout (versión clásica — aún válida para ramas y archivos)
git checkout [rama]                                  # Cambiar a una rama
git checkout -b [rama]                               # Crear y cambiar a una nueva rama
git checkout -                                       # Volver a la última rama en la que estabas
git checkout [hash]                                  # Ir al estado exacto de un commit (modo detached HEAD)

🔗 Git merge — integrar los cambios de una rama en otra

Úsalo cuando quieres combinar el trabajo de dos ramas, por ejemplo al terminar un feature y llevarlo a main.

bashgit merge [rama]                                 # Fusionar la rama indicada en la rama actual
git merge --no-ff [rama]                             # Crear siempre un commit de merge, aunque no sea necesario (trazabilidad)
git merge --squash [rama]                            # Aplastar todos los commits de la rama en uno solo antes de mergear
git merge --abort                                    # Cancelar el merge en curso y volver al estado anterior
git merge --continue                                 # Continuar el merge después de resolver conflictos manualmente
Resolver conflictos de merge — qué hacer cuando dos ramas modificaron el mismo código
Cuando Git reporta un conflicto, los archivos afectados tendrán marcadores como:
<<<<<<< HEAD
tu versión
=======
versión de la otra rama
>>>>>>> feature-branch

Editar el archivo y decidir qué cambios conservar
git add [archivo] para marcar el conflicto como resuelto
git commit para finalizar el merge


 Git rebase — reescribir el historial para mantenerlo limpio y lineal

Úsalo para actualizar tu rama con los últimos cambios de main antes de hacer un pull request, o para limpiar commits locales antes de compartirlos.

bashgit rebase [rama]                                # Reaplica tus commits sobre la punta de otra rama
git rebase -i [hash]                                 # Rebase interactivo: reescribir, unir, reordenar o eliminar commits
git rebase --abort                                   # Cancelar el rebase y volver al estado anterior
git rebase --continue                                # Continuar el rebase después de resolver un conflicto
git rebase --skip                                    # Ignorar el commit actual que generó conflicto y seguir

Merge vs Rebase:

Usa merge para integrar ramas de trabajo — preserva el historial real con todas las bifurcaciones.
Usa rebase para limpiar commits locales antes de hacer push o para mantener un historial lineal y más legible.
 Nunca hagas rebase de commits que ya subiste al remoto y otros comparten.



 Git cherry-pick — traer un commit específico de otra rama sin hacer un merge completo

Útil cuando hay un fix en otra rama que necesitas ahora, sin querer traer todos sus cambios.

bashgit cherry-pick [hash]                           # Aplicar un commit específico a la rama actual
git cherry-pick [hash1] [hash2]                      # Aplicar varios commits sueltos
git cherry-pick [hash1]..[hash2]                     # Aplicar un rango continuo de commits
git cherry-pick --abort                              # Cancelar el cherry-pick en curso
git cherry-pick --continue                           # Continuar tras resolver conflictos manualmente

 Git stash — guardar trabajo a medias para poder cambiar de rama sin hacer commit

Ideal cuando te interrumpen con una tarea urgente y necesitas cambiar de rama con cambios sin terminar.

bashgit stash                                        # Guardar todos los cambios no confirmados temporalmente
git stash -m "mensaje"                               # Guardar con una descripción para identificarlo después
git stash push --include-untracked                   # Incluir también archivos nuevos sin rastrear
git stash list                                       # Ver todos los stashes guardados
git stash apply                                      # Recuperar el último stash sin eliminarlo
git stash pop                                        # Recuperar el último stash y eliminarlo de la lista
git stash drop [nombre]                              # Eliminar un stash específico de la lista
git stash clear                                      # Borrar todos los stashes guardados

 Git tag — marcar versiones o hitos importantes del proyecto (ej: v1.0.0)

Los tags se usan típicamente para marcar releases. A diferencia de las ramas, no avanzan con nuevos commits.

bashgit tag                                          # Listar todas las etiquetas existentes
git tag -n                                           # Listar etiquetas con sus mensajes
git tag [nombre]                                     # Crear una etiqueta ligera (solo un nombre)
git tag -a [nombre] -m "mensaje"                     # Crear una etiqueta anotada (recomendada: incluye autor, fecha y mensaje)
git tag -d [nombre]                                  # Eliminar una etiqueta local
git tag -s [nombre]                                  # Crear etiqueta firmada con GPG (para verificar autoría)
git tag -v [nombre]                                  # Verificar la firma GPG de una etiqueta

git push origin [nombre]                             # Subir una etiqueta específica al remoto
git push origin --tags                               # Subir todas las etiquetas locales al remoto

 Git notes — agregar comentarios a commits existentes sin modificarlos

Útil para añadir contexto, revisiones o notas de deploy a commits ya creados.

bashgit notes add -m "[nota]"                        # Agregar una nota al último commit
git notes add -m "[nota]" [hash]                     # Agregar nota a un commit específico por su hash
git notes show                                       # Mostrar la nota del último commit
git notes list                                       # Listar todos los commits que tienen notas
git notes edit                                       # Editar la nota del último commit (abre el editor)
git notes remove                                     # Eliminar la nota del último commit

 Git remote — gestionar las conexiones a repositorios remotos (GitHub, GitLab, etc.)

Normalmente solo tienes un remoto llamado origin, pero puedes tener varios (ej: upstream para un fork).

bashgit remote                                       # Listar los nombres de los remotos configurados
git remote -v                                        # Listar remotos con sus URLs de fetch y push
git remote add [nombre] [url]                        # Conectar el repositorio local a un remoto nuevo
git remote remove [nombre]                           # Desconectar un remoto
git remote rename [nombre-antiguo] [nombre-nuevo]    # Cambiar el nombre de un remoto
git remote set-url [nombre] [nueva-url]              # Actualizar la URL de un remoto (ej: cambiar de HTTP a SSH)

 Git fetch — descargar cambios del remoto sin tocar tu trabajo local

Es la forma segura de ver qué hay de nuevo en el remoto antes de decidir si fusionas o no.

bashgit fetch                                        # Descargar cambios del remoto principal sin fusionar
git fetch [remoto]                                   # Descargar de un remoto específico
git fetch --all                                      # Descargar de todos los remotos configurados
git fetch --prune                                    # Limpiar referencias locales a ramas remotas ya eliminadas
git fetch --tags                                     # Descargar también todas las etiquetas del remoto

 Git pull — descargar y aplicar cambios del remoto en tu rama actual

Es un git fetch + git merge en un solo paso. Úsalo cuando confías en que no habrá conflictos.

bashgit pull                                         # Descargar y fusionar cambios del remoto en la rama actual
git pull [remoto]                                    # Descargar de un remoto específico
git pull --rebase                                    # Descarga y reaplica tus commits encima (historial más limpio)
git pull --ff                                        # Fusionar solo si es fast-forward; si no, hace merge normal
git pull --ff-only                                   # Fusionar solo si es fast-forward; si no, muestra error y para
git pull --no-ff                                     # Siempre crear un commit de fusión, incluso si no es necesario
git pull --all                                       # Descargar de todos los remotos configurados

 Git push — subir tus commits locales al repositorio remoto

Comparte tu trabajo con el equipo o haz backup de tus cambios en el remoto.

bashgit push                                         # Subir commits de la rama actual al remoto vinculado
git push [remoto]                                    # Subir al remoto especificado
git push [remoto] [rama]                             # Subir una rama específica a un remoto específico
git push -u [remoto] [rama]                          # Primer push: subir la rama y vincularla al remoto (establece upstream)
git push --force-with-lease                          #  Forzar push solo si nadie más subió cambios desde tu último fetch (más seguro)
git push --force                                     #  PELIGROSO: sobreescribe el remoto sin importar lo que haya; puede borrar trabajo de otros

 Git bisect — encontrar qué commit introdujo un bug usando búsqueda binaria

Git divide el historial a la mitad en cada paso hasta encontrar el commit culpable. Muy eficiente en proyectos con cientos de commits.

bashgit bisect start                                 # Iniciar la búsqueda
git bisect bad                                       # Marcar el commit actual como "tiene el bug"
git bisect good [hash]                               # Marcar un commit anterior como "sin bug"
# Git irá saltando entre commits para que los marques como good o bad
git bisect reset                                     # Terminar la búsqueda y volver a tu rama original

 Git reflog — el historial de todo lo que has hecho, incluso lo que "borraste"

El salvavidas de Git. Registra cada vez que el HEAD se mueve — incluso después de un reset --hard, un rebase o borrar una rama. Tienes ~90 días para recuperar cualquier cosa.

bashgit reflog                                       # Ver el historial completo de movimientos del HEAD
git reflog --relative-date                           # Ver el reflog con fechas relativas (ej: "hace 2 horas")
git checkout HEAD@{2}                                # Ir al estado de hace 2 movimientos
git reset --hard HEAD@{1}                            # Restaurar al estado anterior (deshacer el último reset)
git branch [rama-recuperada] HEAD@{3}                # Recrear una rama borrada desde el reflog

Ejemplo práctico: hiciste git reset --hard por error y perdiste commits. Ejecuta git reflog, encuentra el hash del commit perdido y recupéralo con git checkout [hash] o git reset --hard [hash].


 Git grep — buscar texto dentro del código del repositorio

Más rápido que grep normal porque solo busca en archivos rastreados por Git, ignorando node_modules y similares.

bashgit grep "[texto]"                               # Buscar un texto en todos los archivos del repositorio
git grep -n "[texto]"                                # Buscar y mostrar el número de línea
git grep -i "[texto]"                                # Buscar sin distinguir mayúsculas/minúsculas
git grep "[texto]" [hash]                            # Buscar en el estado del repositorio en un commit específico
git grep -l "[texto]"                                # Mostrar solo los nombres de archivos que contienen el texto

 Git clean — eliminar archivos sin rastrear del directorio de trabajo

Útil para limpiar archivos generados automáticamente (builds, logs, temporales) que no están en .gitignore.

bashgit clean -n                                     # Simulación: mostrar qué archivos se eliminarían sin borrar nada
git clean -f                                         # Eliminar archivos sin rastrear (no toca directorios)
git clean -fd                                        # Eliminar archivos y directorios sin rastrear
git clean -fx                                        # Eliminar también archivos ignorados por .gitignore
git clean -fdx                                       # Limpieza total: archivos, directorios e ignorados

⚠️ Siempre ejecuta git clean -n primero para ver qué se va a borrar. Esta operación no se puede deshacer.


 .gitignore — decirle a Git qué archivos nunca debe rastrear

Crea este archivo en la raíz del proyecto antes del primer commit para evitar subir dependencias, credenciales o archivos temporales.

bashtouch .gitignore                                 # Crear el archivo (luego edítalo con tu editor)
Ejemplos de contenido:
gitignore# Dependencias
node_modules/
vendor/

# Variables de entorno y credenciales (¡nunca subir!)
.env
.env.local
*.pem

# Archivos de sistema operativo
.DS_Store
Thumbs.db

# Compilados y builds
dist/
build/
*.pyc

# Logs
*.log

¿Ya estás rastreando un archivo que quieres ignorar?
bashgit rm --cached [archivo]    # Lo quita del repositorio pero lo deja en tu disco
Luego agrégalo al .gitignore y haz commit.