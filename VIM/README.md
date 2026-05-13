### Notas de Vim
Vim es un editor de texto que funciona directamente en la terminal. A diferencia de editores como VS Code o Notepad, no puedes escribir al abrirlo — primero debes entender su sistema de modos.
bashvim [archivo]           # Abrir o crear un archivo
vim +[N] [archivo]      # Abrir en la línea N directamente
vim -R [archivo]        # Abrir en modo solo lectura


# El sistema de modos
El concepto más importante de Vim. Todo gira alrededor de en qué modo estás.
ModoCómo entrarPara qué sirveNormalESC (modo inicial al abrir)Navegar, copiar, borrar, moverseInsercióni desde NormalEscribir y editar textoVisualv desde NormalSeleccionar bloques de textoComando: desde NormalGuardar, salir, buscar y reemplazar

La tecla ESC siempre te devuelve al modo Normal desde cualquier otro modo.


# Modo inserción — escribir texto
Desde el modo Normal, hay varias formas de entrar al modo inserción según dónde quieres empezar a escribir:
vimi          " insertar antes del cursor
a          " insertar después del cursor
o          " insertar en una línea nueva abajo
O          " insertar en una línea nueva arriba
I          " insertar al inicio de la línea
A          " insertar al final de la línea

# Modo normal — navegar y editar
Es el modo por defecto. Nunca escribes texto aquí — solo te mueves y manipulas el contenido.
Navegación
vimh j k l    " moverse: ← ↓ ↑ →
gg         " ir al inicio del archivo
G          " ir al final del archivo
0          " ir al inicio de la línea
$          " ir al final de la línea
w          " saltar al inicio de la siguiente palabra
b          " saltar al inicio de la palabra anterior
[N]G       " ir a la línea N  (ej: 42G va a la línea 42)
Buscar
vim/texto     " buscar hacia adelante
?texto     " buscar hacia atrás
n          " siguiente resultado
N          " resultado anterior
Edición
vimdd         " eliminar la línea completa
D          " eliminar desde el cursor hasta el fin de línea
dw         " eliminar la siguiente palabra
yy         " copiar la línea completa
yw         " copiar la siguiente palabra
p          " pegar debajo / después del cursor
P          " pegar arriba / antes del cursor
u          " deshacer
Ctrl + r   " rehacer
x          " borrar el carácter bajo el cursor
r[c]       " reemplazar el carácter bajo el cursor por c
.          " repetir el último comando

Modo visual — seleccionar texto
Permite seleccionar texto para luego copiarlo, borrarlo o reemplazarlo.
vimv          " selección carácter a carácter
V          " seleccionar líneas completas
Ctrl + v   " selección en bloque (columnas)
Una vez seleccionado:
vimd          " eliminar la selección
y          " copiar la selección
>          " indentar la selección
<          " quitar indentación

Modo comando — guardar y salir
Se accede con : desde el modo Normal.
Guardar y salir
vim:w         " guardar
:wq        " guardar y salir
:x         " guardar y salir (solo si hubo cambios)
:q         " salir (solo si no hay cambios sin guardar)
:q!        " salir descartando todos los cambios
:w !sudo tee %  " guardar como superusuario si abriste sin permisos
Otros comandos útiles
vim:u         " deshacer
:set nu    " mostrar números de línea
:set nonu  " ocultar números de línea
:N         " ir a la línea N  (ej: :42)
:%s/a/b/g  " reemplazar todas las ocurrencias de 'a' por 'b'

Flujo básico de uso
1. vim archivo.txt          → abres el archivo en modo Normal
2. i                        → entras al modo Inserción
3. (escribes tu contenido)
4. ESC                      → vuelves al modo Normal
5. :wq                      → guardas y sales

Si en algún momento no sabes en qué modo estás, presiona ESC una o dos veces — siempre te lleva de vuelta al modo Normal.