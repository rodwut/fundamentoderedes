
## Objetivo

Comprobar que dos equipos con direcciones del mismo bloque pueden estar en la misma red o en redes distintas según la máscara que se les asigne.

## Material

- 2 PCs
- 1 switch 2960
- 2 cables de cobre directos (Copper Straight-Through)

## Antes de abrir Packet Tracer: calcula

Completa esta tabla en papel con las dos máscaras. Usa el método del bloque y la operación AND.

| Equipo | IP             | Máscara               | Dirección de red (AND) | Broadcast (OR) | Rango de hosts                             |
| ------ | -------------- | --------------------- | ---------------------- | -------------- | ------------------------------------------ |
| PC0    | 192.168.10.70  | 255.255.255.0 (/24)   | 192.168.10.0           | 192.168.10.255 | 192.168.10.1 – 192.168.10.254 (254 hosts)  |
| PC1    | 192.168.10.130 | 255.255.255.0 (/24)   | 192.168.10.0           | 192.168.10.255 | 192.168.10.1 – 192.168.10.254 (254 hosts)  |
| PC0    | 192.168.10.70  | 255.255.255.192 (/26) | 192.168.10.64          | 192.168.10.127 | 192.168.10.65 – 192.168.10.126 (62 hosts)  |
| PC1    | 192.168.10.130 | 255.255.255.192 (/26) | 192.168.10.128         | 192.168.10.191 | 192.168.10.129 – 192.168.10.190 (62 hosts) |

**Predicción:** ¿en cuál de los dos casos crees que las PCs se verán entre sí? Anótalo antes de probar: __________________

## Parte 1. Armar la red

1. Agrega 2 PCs y 1 switch 2960.
2. Conecta cada PC al switch con un cable de cobre directo: PC0 al puerto FastEthernet0/1 y PC1 al FastEthernet0/2.
3. Espera a que los enlaces se pongan en verde.

## Parte 2. Prueba con máscara /24

1. Haz clic en PC0, ve a **Desktop > IP Configuration** y escribe:
   - IPv4 Address: `192.168.10.70`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: déjalo vacío
2. En PC1 escribe:
   - IPv4 Address: `192.168.10.130`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: déjalo vacío
3. En PC0, abre **Desktop > Command Prompt** y ejecuta `ping 192.168.10.130`.
4. Anota el resultado: __________________

## Parte 3. Prueba con máscara /26

1. En **las dos PCs** cambia solo la máscara a `255.255.255.192`. Las IP no cambian.
2. En PC0 ejecuta de nuevo `ping 192.168.10.130`.
3. Anota el resultado: __________________
4. Ejecuta `ipconfig` en cada PC y confirma la IP y la máscara que tiene configuradas.

## Parte 4. Observa los paquetes (modo Simulación)

1. Cambia a **Simulation** (esquina inferior derecha).
2. En **Edit Filters** deja activos solo **ICMP** y **ARP**.
3. Repite el ping de PC0 a PC1 con la máscara /26.
4. Anota qué paquetes aparecen en la lista de eventos, o si no aparece ninguno: __________________
5. Cambia las dos PCs otra vez a /24, repite el ping y compara con lo que viste en el paso anterior.

## Parte 5. Arregla la comunicación con /26

Con la máscara /26, cambia la IP de **PC1** a una dirección que sí quede en la misma red que PC0.

1. Escribe la IP que elegiste: __________________
2. Haz ping desde PC0 y anota el resultado: __________________

## Preguntas

1. Las dos PCs tienen las mismas IP en las Partes 2 y 3. ¿Por qué el ping funciona con /24 y falla con /26?
   **R:** Con /24 las dos quedan en la misma red (192.168.10.0). Con /26 quedan en redes distintas y, sin gateway, no pueden comunicarse.
2. Con /26, ¿a qué red pertenece PC0 y a cuál PC1?
   **R:** PC0 pertenece a 192.168.10.64 y PC1 a 192.168.10.128.
3. Con /26 y PC0 en 192.168.10.70, ¿qué rango de direcciones puede usar PC1 para comunicarse con ella?
   **R:** De 192.168.10.65 a 192.168.10.126, sin usar la .70.
4. Si cada equipo usara un **switch distinto** con /26, ¿qué dispositivo haría falta para que se comunicaran y qué dato tendrían que configurar las PCs?
   **R:** Haría falta un router, y cada PC tendría que configurar su Default Gateway.

## Reto opcional

Con máscara /26, asigna a PC1 la dirección `192.168.10.127`. Anota qué ocurre y explica por qué esa dirección no debe usarse en un equipo.

## Entregable

- Tabla de cálculo completa.
- Captura del ping exitoso con /24 y del ping fallido con /26.
- Captura de la lista de eventos en modo Simulación.
- Respuestas a las 4 preguntas.

---
