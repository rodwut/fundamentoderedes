El cliente obtiene su configuracion en cuatro pasos, DORA: Discover, Offer, Request y Acknowledfe. El primer mensaje es un broadcast.

El servidor entrega. IP, mascara, puerta de enlace y DNS.

## Para que sirve DHCP.

DCHP (protocolo de configuracion dinamica de host) es un servicio que asigna direcciones IP automaticamente a los equipos de la red.
Evita configurar cada equipo y los conflictos por direcciones duplicadas.

## Los cuatro mensajes de DHCP.

| Paso | Mensaje     | Quien lo envia      | Que hace                            |
| ---- | ----------- | ------------------- | ----------------------------------- |
| 1    | Discover    | Cliente             | Busca un servidor DHCP en la red    |
| 2    | Offer       | Servidor            | Ofrece una direccion IP disponible  |
| 3    | Request     | Cliente (broadcast) | Pide la direccion ofrecida          |
| 4    | Acknowledge | Servidor            | Confirma y entrega la configuracion |

## Tiempo de concesion

La direccion se entrega en prestamo por un tiempo de concesion (lease), no de forma permanente.
El cliente renueva a la mitad del tiempo; en windows, ipconfig /release libera la direccion e ipconfig /renew pide otra.

## El pool de direcciones

El servidor reparte direcciones de un pool (rango) y entrega con ella la mascara, lapuerta de enlace y el DNS.

Las direcciones fijas de servidores, impresoras y routers se excluyen del pool, o se reservan por direccion MAC.


## Puertos y relevo de DHCP

DHCP usa UDP: el servidor escucha en el puerto 67 y el cliente en el 68.
El broadcast no cruza routers: un router con ip helper-address reenvia las solicitudes a un servidor en otra red (reLay).