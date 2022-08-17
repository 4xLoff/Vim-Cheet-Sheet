                                                                Vim-Cheet-Sheet.



Basicos.

Movimiento del cursor (modo normal/visual).

h j k l                   - Teclas de flecha.
w/ b                      - Palabra siguiente/anterior.
W/ B                      - Palabra siguiente/anterior (separados por espacios).
e/ ge                     - Fin de palabra siguiente/anterior.
0/ $                      - Inicio/Fin de línea.
^                         - Primer carácter que no está en blanco de la línea (igual que 0w).
Edición de texto.

i/ a                      - Iniciar el modo de inserción en/después del cursor.
I/ A                      - Iniciar el modo de inserción al principio/final de la línea.
o/ O                      - Agregar línea en blanco debajo/arriba de la línea actual.
Esco Ctrl+[               - Salir del modo de inserción.
d                         - Borrar.
dd                        - Eliminar línea.
c                         - Eliminar, luego iniciar el modo de inserción.
cc                        - Eliminar línea, luego iniciar el modo de inserción.

Operadores.

Los operadores también trabajan en Modo Visual.

d                         - Elimina desde el cursor hasta la ubicación del movimiento.
c                         - Elimina desde el cursor hasta la ubicación del movimiento, luego inicia el modo de inserción.
y                         - Copiar desde el cursor a la ubicación de movimiento.
\>                         - Sangrar un nivel.
<                         - Unindent un nivel.

También puede combinar operadores con movimientos. Ej: d$elimina desde el cursor hasta el final de la línea.

Marcar texto (modo visual).

v                         - Iniciar modo visual.
V                         - Iniciar el modo visual en línea.
Ctrl+v                    - Iniciar el modo de bloqueo visual.
Esco Ctrl+[               - Salir del modo visual.

Portapapeles.

yy                        - Yank (copiar) una línea.
p                         - Pegar después del cursor.
P                         - Pegar antes del cursor.
dd                        - Eliminar (cortar) una línea.
x                         - Eliminar (cortar) el personaje actual.
X                         - Eliminar (cortar) carácter anterior.
d/ c                      - Por defecto, estos copian el texto borrado.

saliendo.

:w                        - Escribe (guarda) el archivo, pero no salgas.
:wq                       - Escribir (guardar) y salir.
:q                        - Salir (falla si algo ha cambiado).
:q!                       - Salir y desechar los cambios.

Buscar/Reemplazar.

/pattern                  - Buscar patrón.
?pattern                  - Buscar patrón hacia atrás.
n                         - Repita la búsqueda en la misma dirección.
N                         - Repita la búsqueda en dirección opuesta.
:%s/old/new/g             - Reemplace todo lo antiguo con nuevo en todo el archivo ( aunque gn es mejor).
:%s/old/new/gc            - Reemplace todo lo antiguo por nuevo en todo el archivo con confirmaciones.

General.

u                         - Deshacer.
Ctrl+r                    - Rehacer.

Avanzados.

Movimiento del cursor.

Ctrl+d                    - Bajar media página.
Ctrl+u                    - Subir media página.
}                         - Avanzar por párrafo (la siguiente línea en blanco).
{                         - Ir hacia atrás por párrafo (la siguiente línea en blanco).
gg                        - Ir a la parte superior de la página.
G                         - Ir al final de la página.
: \[num\] \[enter\]       - Ir a esa línea en el documento.
ctrl+e / ctrl+y           - Desplazarse hacia abajo/arriba una línea.

Búsqueda de personajes.

f \[char\]                - Avanzar al carácter dado.
F \[char\]                - Mover hacia atrás al carácter dado.
t \[char\]                - Avanzar hasta antes del carácter dado.
T \[char\]                - Mover hacia atrás hasta antes del carácter dado.
;/ ,                      - Repetir búsqueda hacia delante/hacia atrás.

Edición de texto.

J                         - Unir la línea de abajo a la actual.
r \[char\]                - Reemplace un solo carácter con el carácter especificado (no usa el modo Insertar).

Modo visual.

O                         - Mover a otra esquina del bloque.
o                         - Mover al otro extremo del área marcada.

Pestañas de archivo.

:e filename               - Editar un archivo.
:tabe                     - Hacer una nueva pestaña.
gt                        - Ir a la siguiente pestaña.
gT                        - Ir a la pestaña anterior.
:vsp                      - Ventanas divididas verticalmente.
ctrl+ws                   - Ventanas divididas horizontalmente.
ctrl+wv                   - Ventanas divididas verticalmente.
ctrl+ww                   - Cambiar entre ventanas.
ctrl+wq                   - Salir de una ventana.

Marcas.

Las marcas le permiten saltar a puntos designados en su código.

m{a-z}                    - Establecer marca {az} en la posición del cursor.

Una marca mayúscula {AZ} establece una marca global y funcionará entre archivos.

'{a-z}                    - Mueva el cursor al inicio de la línea donde se estableció la marca.
''                        - Volver a la ubicación de salto anterior.

Objetos de texto.

Digamos que tiene def (arg1, arg2, arg3), donde el cursor está en algún lugar en medio del paréntesis.
di(elimina todo lo que está entre paréntesis. Eso dice "cambiar todo dentro del paréntesis más cercano". 
Sin objetos de texto, tendría que hacer T(dt).

General.

.                         - Repetir el último comando.
Ctrl+r + 0en              - el modo de inserción inserta el último texto extraído (o en el modo de comando).
gv                        - volver a seleccionar (seleccionar el último bloque de texto seleccionado, desde el modo visual).
%                         - salta entre emparejar ()o{}.