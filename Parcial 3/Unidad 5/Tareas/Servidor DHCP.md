# Práctica: Servidor DHCP


## Objetivo

Comprobar cuántos equipos admite una red según su máscara (/30, /29 y /28) usando un servidor DHCP, y aplicar la fórmula de hosts útiles.

## Material

- 1 servidor (Server-PT)
- 1 switch 2960
- Hasta 14 PCs (se agregan poco a poco)
- Cables de cobre directos (Copper Straight-Through)

## Antes de abrir Packet Tracer: calcula

La red que vas a usar es 192.168.50.0. El **servidor** ocupará la primera dirección útil (192.168.50.1) con IP fija, así que **esa dirección ya no está disponible para las PCs**.

Completa en papel las columnas de cálculo con la fórmula de hosts útiles.

| Prefijo | Máscara | Bits de host (h) | Hosts útiles | Direcciones disponibles para PCs (sin el servidor) |
|---|---|---|---|---|
| /30 | 255.255.255.252 | 2 | 2² − 2 = 2 | 2 − 1 = 1 |
| /29 | 255.255.255.248 | 3 | 2³ − 2 = 6 | 6 − 1 = 5 |
| /28 | 255.255.255.240 | 4 | 2⁴ − 2 = 14 | 14 − 1 = 13 |

**Predicción:** ¿cuántas PCs crees que recibirán IP en cada caso? Anótalo antes de probar: /30 → 1 PC, /29 → 5 PCs, /28 → 13 PCs

## Parte 1. Armar la red

1. Agrega el servidor y el switch 2960.
2. Conecta el servidor al switch con un cable de cobre directo.
3. Agrega una PC y conéctala al switch. Para tener más, copia y pega la PC (Ctrl+C, Ctrl+V) y conecta cada una al switch.
4. Todas las PCs van al mismo switch. Espera a que los enlaces se pongan en verde.

## Parte 2. Prueba con máscara /30

### 2.1 Configura el servidor

1. Haz clic en el servidor, ve a **Desktop > IP Configuration** y escribe:
   - IPv4 Address: `192.168.50.1`
   - Subnet Mask: `255.255.255.252`
   - Default Gateway: déjalo vacío
2. Ve a **Services > DHCP** y activa el servicio (**Service: On**).
3. En el pool (puedes editar el que viene por defecto, `serverPool`) escribe:
   - Default Gateway: `0.0.0.0`
   - DNS Server: `0.0.0.0`
   - Start IP Address: `192.168.50.2`
   - Subnet Mask: `255.255.255.252`
   - Maximum Number of Users: el valor que calculaste en la última columna de tu tabla
4. Pulsa **Save**.

### 2.2 Conecta las PCs de una en una

1. En la primera PC, ve a **Desktop > IP Configuration** y selecciona **DHCP**.
2. Anota la IP que recibió: __________________
3. Repite con una segunda PC y con las siguientes, una por una, hasta que alguna **ya no reciba IP**.
4. Anota cuántas PCs recibieron IP: __________________
5. En la PC que no recibió IP, anota qué dirección o mensaje muestra: __________________

## Parte 3. Repite con /29

1. En el servidor cambia la máscara de su IP fija a `255.255.255.248`.
2. En **Services > DHCP** cambia la máscara del pool a `255.255.255.248`, el Maximum Number of Users al valor que calculaste para /29 y pulsa **Save**.
3. En cada PC cambia a **Static** y vuelve a seleccionar **DHCP** para que pida una IP nueva.
4. Conecta o activa las PCs de una en una hasta que una ya no reciba IP. Agrega PCs nuevas si hace falta.
5. Anota cuántas recibieron IP: __________________

## Parte 4. Repite con /28

Repite la Parte 3 con la máscara `255.255.255.240` y el Maximum Number of Users que calculaste para /28.
Anota cuántas PCs recibieron IP: __________________

## Parte 5. Resultados

Completa la tabla con lo que observaste:

| Prefijo | Hosts útiles | PCs que recibieron IP (observado) | ¿Coincide con tu predicción? |
|---|---|---|---|
| /30 | 2 | | |
| /29 | 6 | | |
| /28 | 14 | | |

## Parte 6. Sin probar: aplica la fórmula

Calcula en papel, sin probarlo en Packet Tracer:

| Prefijo | Máscara | Bits de host | Hosts útiles | PCs que caben junto al servidor |
|---|---|---|---|---|
| /27 | 255.255.255.224 | 5 | 2⁵ − 2 = 30 | 29 |
| /26 | 255.255.255.192 | 6 | 2⁶ − 2 = 62 | 61 |
| /24 | 255.255.255.0 | 8 | 2⁸ − 2 = 254 | 253 |

## Preguntas

1. En /30, ¿por qué la red solo admite una PC si la fórmula da 2 hosts útiles?
   **R:** Porque una de esas 2 direcciones útiles (192.168.50.1) ya la ocupa el servidor con su IP fija. Solo queda libre la 192.168.50.2, que es la que el DHCP entrega a una PC.
2. ¿Qué dos direcciones de cada red nunca se pueden asignar a un equipo y por qué?
   **R:** La **dirección de red** (todos los bits de host en 0), que identifica a la red, y la **dirección de broadcast** (todos los bits de host en 1), que sirve para enviar un mensaje a todos los equipos de la red. Por ejemplo, en 192.168.50.0/30 son la .0 y la .3.
3. Si en una red /30 también conectas un router como puerta de enlace, ¿cuántas PCs caben junto con el servidor? Explica.
   **R:** Ninguna (0). La /30 solo tiene 2 direcciones útiles: una sería para el servidor y la otra para el router. No queda ninguna libre para una PC.
4. Una oficina tiene 20 PCs y un servidor. ¿Cuál es la máscara más pequeña (con menos direcciones) que sirve y por qué?
   **R:** La **/27 (255.255.255.224)**. Se necesitan 21 direcciones (20 PCs + 1 servidor). La /28 solo da 14 hosts útiles, que no alcanzan. La /27 da 2⁵ − 2 = 30 hosts útiles, así que caben los 21 equipos y sobran 9 direcciones (por ejemplo, para un router).

## Entregable

- Tabla de cálculo con la predicción.
- Capturas de la pantalla de **Services > DHCP** en cada máscara.
- Captura de la PC que no recibió IP en cada caso.
- Tablas de las Partes 5 y 6 completas.
- Respuestas a las 4 preguntas.

---
