La direccion MAC es el identificador de 48 bits que tiene cada tarjeta de red y que sirve para identificar el origen y el destino de una trama dentro de la LAN.

![[Pasted image 20261105152048.png|564]]

## Como se escribe la MAC
Se escribe con 12 digitos hexadecimales, por ejemplo 00:1A:2B:3C:4D:5E. El formato cambia segun el sistema: con guiones en windows (00-1A-2B-3C-4D-5E) y con puntos en Cisco (00.1A.2B.3C.4D.5E).

## La MAC se puede cambiar 
Viene grabada de fabrica en la tarjeta, pero el sistema operativo puede modifcarla por software. Por eso no debe ser el unico mecanismo de seguridad (MAC spoofing).

## Para que sirve la MAC
los switches usan la MAC para decidir por que puerto reenviar cada trama y construyen su tabla de direcciones aprendiendo la MAC de origen.

## Unicast, multicast y broadcast
Segun a cuantos equipos va dirigida, una comunicacion puede ser unicast (a uno), multicast (a un grupo) o broadcast (a todos).

### Unicast: de uno a uno
La trama va a un solo destinatario, identificado por su MAC especifica; es el tipo de trafico mas comun, como abrir una pagina web o copiar un archivo.
#### Unicast en el switch
El switch busca la MAC de destino en su tabla de direcciones y envia la trama solo por el puerto donde esta ese equipo; si no la conoce, la inunda por todos los puertos.
### Multicast: de uno a un grupo
La trama va a un grupo de equipos que se unieron a el; los demas la ignoran. En IPv4 usa direcciones 224.0.0.0 a 239.255.255.255 y MAC que empiezan con 01:00:5E

### Broadcast: de uno a todos
La trama llega a todos los equipos de la red, con MAC de destino FF:FF:FF:FF:FF:FF todos la reciben y la procesan

#### Para que sirve el unicast
Sirve para enviar el mismo contenido a muchos receptores.
