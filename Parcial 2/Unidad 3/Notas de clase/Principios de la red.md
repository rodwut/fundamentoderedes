## Principio: Componentes
La capa fisica se compone de tres elementos: los **medios fisicos** (cables, conectores y dispositivos), la **codificacion** de los datos y la **señalizacion** que los transmite 

## Parametros
Su desempeño se mide con 3 parametros, el ancho de banda (capacidad maxima), el rendimiento (lo que realmente se transfiere) y la latencia


# Tipos de Cables
## Tipos de cable: cobre
El cable de par trenzado (UTP) transmite señales electricas con conectores RJ-45, alcanza hsta 100 metros y es el mas usado 

#### UTP: ¿por que los cables van en pares?
los 8 hilos del UTP forman 4 pares trenzados. Cada par envia señal con polaridad opuesta en sus dos hilos; la interferencia afecta a ambos por igual y el receptor la cancela al comparar los dos.


## Tipos de cable: Fibra optica 
La fibra oprica transmite pulsos de luz: llega a mayores distancias y es inmune a la interferencia electromagnetica pero es mas costosa y delicada de instalar.

## Medios inalambricos
Transmiten por ondas de radio (Wi-fi
Bluetooth, celular): dan movilidad, pero el medio compartido, sufre interferencias y requiere medidas de seguridad

## Capa Fisica: señales de comunicacion
Una señal es una variacion de una propiedad fisica que representa bits; cambios de voltaje en cobre, pulsos de luz en fibra optica u ondas de radio en el aire 

## Señalizacion y codificacion fisica
La codificacion convierte los bit en un patron  predefinido que facilita la sincronia y la deteccion de errores; la señalizacion define como se representa ese patron en el medio.

## Medios Fisicos: Conexion de la comunicacion
Un dispositio se conecta mediante su tarjeta de red (NIC), un puerto, un conector y el medio; la NIC convierte los bits en la señal que el medio puede transportar.

# Ethernet capa 1 y 2 
Ethernet (IEEE 802.3) es el estandar dominante en LAN y trrabaj en dos capas: en la capa 1 define medios y señalizacion, y en la capa 2 define las tramas y las direcciones MAC.

## ARP: de direccion IP a direccion MAC
El protocolo ARP permite descurir la direccion MAC de un dispositico a partis de su direccion IP. Envia una peticion por broadcast, solo el dueño de esa IP responde por unicast, y el resultado se guarda en la tabla ARP.

## Envenenamiento ARP (ARP poisoning)
ARP no verifica quien responde: un atacante encia respuesta ARP falsas para que otros equipos asocien su MAC con la IP de otros dispositivos, por ejemplo la del router, y asi intercepta el trafico (ataque de intermediario).

