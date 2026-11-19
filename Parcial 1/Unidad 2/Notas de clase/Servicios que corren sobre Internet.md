Internet es la infraestructura, la Web, el correo electronico, el streaming y la mensajeria son aplicaciones que se ejecutan sobre ella, no la red misma.

![[Viaje de datos Backbone.png]]

## *Porque se considera una infraestrucutra el internet?*
*Funciona como una base fisica y logica que sustenta la mayoria de los servicios de la actualidad*





# Modelo TCP/IP
Modelo de cuatro capas que describe como se comunican los dispositvios en una red real; a diferencia de OSI, si se implementa yal cual en internet y en la mayoria de las redes actuales.

Nacio parte del proyecto ARPANET en los años 70s, antes que el modelo OSI; por eso es el modelo practico, construido desde la implementacion y no desde la teoria.

### Capa de Aplicacion
Es donde viven los progamas y servicios que el usuario reconoce: navegador web, correo, mensajeria. Agrupa lo que en OSI son tres capas separadas: aplicacion, presentacion y sesion.

### Capa de transporte
Divide el mensaje en segmentos, agrega numero de puerto de origen y destino, y decide si la entrega necesita confirmacion (TCP) o no (UDP)