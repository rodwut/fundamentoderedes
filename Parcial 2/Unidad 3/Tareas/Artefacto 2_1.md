Nombre: Rodrigo Espino Juárez

Campo 1
Dato de ejemplo: 10101010 10101010 10101010 10101010 10101010 10101010 10101010 10101011 (8 bytes)
Nombre del campo: Preambulo
Para qué sirve: sincroniza los dispositivos emisores y receptores haciendo que estos se preparen para una trama nueva

Campo 2
Dato de ejemplo: FFFF.FFFF.FFFF (6 bytes)
Nombre del campo: Direccion MAC de destino
Para qué sirve: es la direccion de transmision

Campo 3
Dato de ejemplo: 0001.4321.ABCD (6 bytes)
Nombre del campo: Direccion MAC de origen
Para qué sirve: indentifica el dispositivo que envia la trama, asi el receptor sabe donde responder

Campo 4
Dato de ejemplo: 0x0806 (2 bytes)
Nombre del campo: Ethertype
Para qué sirve: Indica que protocolo de la capa superior viaja dentro de la trama

Campo 5
Dato de ejemplo: ¿Quién tiene la IP 192.168.1.2? Responde a 192.168.1.1 (entre 46 y 1500 bytes)
Nombre del campo: Payload
Para qué sirve: informacion que transporta la trama

Campo 6
Dato de ejemplo: 0x3A7F91C2 (4 bytes)
Nombre del campo: Frame Check Sequence
Para qué sirve: Detecta errores mas no los corrige
