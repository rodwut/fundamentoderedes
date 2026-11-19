Toda dirección tiene dos partes: la parte de red, igual para todos los equipos del grupo, y la parte de host, que identifica a cada equipo.

![[Pasted image 20261117192137.png]]

## Direcciones publicas
Las direcciones publicas son unicas en todo Internet y las asigna el proveedor de servicio (ISP).

Un equipo con direccion publica es alcanzable desde Internet; las privadas no.

![[Pasted image 20261117192256.png|520]]

## Direcciones privadas
Se usan solo dentro de una red y no se enrutan en Internet: 10.0.0.0/8, 172.16.0.0/12 y 192.168.0.0/16. Para salir a internet usan NAT.

## Direcciones especiales
127.0.0.1 es el loopback(el propio equipo) y 169.254.0.0/16 es la asignacion automatica (APIPA) cuando falla el DHCP.

0.0.0.0/0 es la ruta prederminada.

## Direcciones IPv4
Una direccion Ipv4 tiene 32 bits escritos en 4 octetos decimales separados por puntos, como 192.168.1.10; una parte identifica la red y la otra el host