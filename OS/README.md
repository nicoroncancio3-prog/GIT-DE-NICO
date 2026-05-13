### Comandos de Linux
Referencia rápida de comandos esenciales para la terminal de Linux.

Navegación y directorios
pwd
Muestra la ruta completa del directorio donde te encuentras actualmente.
bashpwd
# Ejemplo de salida: /home/usuario/proyectos
mkdir <nombre>
Crea una nueva carpeta en la ubicación actual.
bashmkdir proyectos
mkdir -p proyectos/web/css   # Crea carpetas anidadas de una vez
cd <nombre>
Entra a una carpeta.
bashcd documentos       # Entrar a una carpeta
cd ..               # Subir al directorio anterior
cd ~                # Ir al directorio home
cd /ruta/completa   # Ir a una ruta absoluta
ls / ls -la
Lista los archivos y carpetas del directorio actual.
bashls          # Lista archivos y carpetas visibles
ls -la      # Muestra archivos ocultos, permisos, dueño y tamaño
ls -lh      # Igual que -la pero con tamaños legibles (KB, MB)

Archivos
touch <archivo>
Crea un archivo vacío o actualiza la fecha de modificación de uno existente.
bashtouch notas.txt
touch index.html style.css   # Crear varios a la vez
cat <archivo>
Muestra el contenido de un archivo en la terminal.
bashcat notas.txt
cat archivo1.txt > archivo2.txt   # Copiar contenido

Para archivos largos, usa less <archivo> en su lugar — permite desplazarte con las flechas.

rm -rf <ruta>
Elimina archivos o carpetas de forma recursiva y sin confirmación.
bashrm archivo.txt          # Eliminar un archivo
rm -rf carpeta_vieja    # Eliminar carpeta y todo su contenido

⚠️ Precaución: No hay papelera de reciclaje. La acción es permanente e irreversible.


Terminal
clear
Limpia la pantalla de la terminal.
bashclear
# Atajo equivalente: Ctrl + L
htop
Monitor interactivo de procesos, uso de CPU y RAM en tiempo real. Más visual que top.
bashhtop
# Salir: presiona q
# Instalar: sudo apt install htop

Información del sistema
cat /etc/os-release
Muestra información de la distribución Linux instalada: nombre, versión y otros detalles.
bashcat /etc/os-release
# Ejemplo de salida:
# NAME="Ubuntu"
# VERSION="22.04.3 LTS (Jammy Jellyfish)"

Referencia rápida
ComandoDescripciónpwdVer directorio actualmkdir <nombre>Crear carpetacd <nombre>Entrar a carpetacd ..Subir al directorio anteriorcd ~Ir al homelsListar archivos visiblesls -laListar con detalles y ocultostouch <archivo>Crear archivo vacíocat <archivo>Ver contenido de archivorm -rf <ruta>Eliminar archivo o carpetaclearLimpiar terminalhtopMonitor de procesoscat /etc/os-releaseInfo del sistema operativo