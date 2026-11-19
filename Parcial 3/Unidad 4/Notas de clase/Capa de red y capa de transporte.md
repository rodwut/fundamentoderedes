## IPv4
IPv4 es el protocolo de la capa de red que direcciona y enruta los paquetes entre redes, usando direcciones 
### Historia de IPv4
IPv4 se definio en 1981 (RFC 791) dentro de la familia TCP/IP, diseñada por Vint Cerf Bob Kahn.

En 1983 ARPENET adopto TCP/IP, el origen de lo que hoy es Internet.

## Como se agotaron las direcciones 
Las 4.300 millones de direciones parecian suficientes, pero se repartieron en bloques por clases; una Clase A daba mas de 16 millones a una sola organizacion. Ademas, los dispositivos conectados crecieron sin parar.
En 2011 la IANA entrego sus ultimos bloques a los registros regionale. Se alargo la vida de IPv4 con CIDR, las direcciones privadas y NAT; la solucion definitiva es IPv6

## Diferencias entre IP publica e IP privada

| Caracteristica   | IP publica                                 | IP privada                                              |
| ---------------- | ------------------------------------------ | ------------------------------------------------------- |
| Qonde se usa     | En todo internet                           | En la red de WiFi local en la casa                      |
| Quien la asigna  | El proveedor de servicio de Internet (ISP) | El router dentro de la red local                        |
| Visibilidad      | Visible para el exterior                   | Oculta al exterior (solo visible en la red local)       |
| Unicidad         | Unica en todo el mundo                     | Unica solo en la red local (se reutiliza en otras reds) |
| Rango habituales | Varias segun la asignacion del ISP         | 10.x.x.x, 172.16.x.x – 172.31.x.x, 1s 92.168.x.x        |

## Caracteristicas de IPv4 
Es sin conexion (cada paquete viaja por separado), de mejor esfuerzo (no garantiza la entrega) e independiente del medio (funciona sobre cobre, fibra o WiFi).

### Encabezado IPv4
El encabezado mide 20 bytes como minimo y lleva la IP de origen, la IP de destino, el TTi (limite de saltos) y el campo protocolo (TCP, UDP o ICMP).

## IPv6 
IPv6 usa direcciones de 128 bits y se creo porque las direcciones IPv4 es agotaron, permite un numero practicamente ilimitado de dispositivos.

### Cuantas direcciones tiene IPv6
Con 128 bits hay 2^128 direcciones: unos 340 sextillones (3.4x10^38), es deicr, 2^96 mas que IPv4.
Cada subred estandar (/64) por si sola tiene 2^64 direcciones, mas de 18 trillones

### Ventajas de IPv6 
Ofrece un espacio de direcciones enorme, un encabezado simplificado de 40 bytes, autoconfiguracion de direcciones y no usa broadcast: lo remplaza el multicast.

## Division de la red en grupos
Una red grande se divide en subredes: grupos de dispositivos organizados por ubicacion, funcion o departamento, cada uno con su propio rango de direcciones