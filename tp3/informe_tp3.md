# Comunicaciones de Datos Laboratorio N°3

**Integrantes:**

 _Federico Cechich_

 _Facundo Guerrero_

 _Ignacio J. Vigezzi_

**Nombre del grupo**: _Comunicadores-Seriales_

**Universidad Nacional de Cordoba**

**Facultad de Ciencias Exactas, Fisicas y Naturales**

**Asignatura:** Comunicaciones de datos

**Profesores:** Facundo Oliva Cuneo y Santiago Martín Henn

**Fecha:** 29/09/2025

---

**Informacion de contacto**: _Cechich Federico - federico.cechich@mi.unc.edu.ar_
                             _Guerrero Facundo - facundo.guerrero.pozzi@mi.unc.edu.ar_
                             _Vigezzi Ignacio - ignacio.vigezzi@mi.unc.edu.ar_

## 1)

### a)

IEEE 802.3: La primera edición fue aprobada por la IEEE en 1983, por ANSI en 1984 y publicada en 1985. Surge como la estandarización de Ethernet bajo el nombre 10BASE5 con velocidades de 10 Mbits/s sobre cable coaxial. Fue evolucionando a lo largo de los años con mejoras de velocidad de transferencia de datos y utilización de nuevos medios físicos. Algunos eventos destacables son: 

- implementación de cable trenzado no blindado (UTP) en 1990 bajo la norma 802.3j y el sub estándar 10BASE-T

- implementación de fibra óptica en 1993 como 10BASE-F

- transmisión a 100 MBits/s con autonegociación de velocidad bajo las denominaciones 100BASE-TX, 100BASE-4 y 100BASE-FX, con el nombre Fast Ethernet

- Extensión de tamaño máximo de trama para implementación de Q-tag en 1998

- Implementación de Power over Ethernet para alimentación de dispositivos utilizando el mismo cable de red en 2003

IEEE 802.11: Aprobado en 1987 para conexiones de red de área local (LAN) y define las especificaciones de los medios físicos y el control de acceso del medio (MAC) para redes locales inalámbricas (WLAN). La primera versión contaba con velocidades de entre 1 y 2 MBits/s y utilizaba la banda de 2.4GHz. Algunos eventos destacables son:

- Mejora de velocidad hasta 11 MBits/s en 1999

- Implementación de la banda de 5GHz con velocidades de hasta 64 MB/s en 1999 como 802.11a

- Implementación de Wi-Fi 5 con velocidades de más de 6000 MBits/s en 2013 como 802.11ac

- Implementación de Wi-Fi 6 y posteriormente 6E en 2021 bajo norma 802.11ax

### b)
Al conectarlos a la red FCEFyN 2.4GHz observamos que utiliza la versión del protocolo 802.11b/g que permite solo 2.4 GHz y velocidades bajas (<54 Mbps).

<img width="842" height="377" alt="image" src="https://github.com/user-attachments/assets/a373b27f-88c5-47e7-a328-153ee1b2975b" />

Imagen 1.1

Además, tanto la red FCEFyN 5 GHz como unc-libre utilizan la versión de protocolo 802.11ax o WiFi 6

<img width="912" height="466" alt="image" src="https://github.com/user-attachments/assets/b80859e8-8227-4478-8bbe-827f77132190" />

Imagen 2.2

<img width="918" height="467" alt="image" src="https://github.com/user-attachments/assets/cbf2fd15-3592-43aa-8b99-f5d3ad5b0b81" />

Imagen 2.3

### c)
Si una NIC no es compatible con el protocolo utilizado por la red no podrá interpretar los paquetes que circulan por el medio, y por lo tanto, no podrá conectarse a la misma o incluso puede no ser compatible con el mismo medio, sea el caso de una NIC que solo tiene soporte para Ethernet y es imposible de conectar a una red inalámbrica basada en el estándar IEEE 802.11

### d)

Cada nueva versión de protocolo incorpora mejoras de seguridad.

- Wi-Fi 5 (802.11ac): Utiliza Wi-Fi Protected Access 2 (WPA2), que implementa cifrado mediante AES (Advanced Encryption Standard)

- Wi-Fi 6 (802.11ax): Implementa WPA3 que utiliza encriptación más robusta mediante cifrado de 128 bits en modo WPA3-Personal ademas de Simultaneous Authentication of Equals (SAE) y Opportunistic Wireless Encryption (OWE)

- Wi-Fi 7 (802.11be): Utiliza WPA3 con la intención de implementar WPA4 en el futuro

Las tres redes de la facultad son abiertas, es decir, no utilizan protocolos de seguridad como WPA2 o WPA3. Sin embargo, las redes con Wi-Fi 6 pueden ser configuradas para utilizar OWE, diseñado para redes abiertas, que permite el cifrado de la comunicación entre el dispositivo conectado y el punto de acceso a pesar de no tener contraseña

### e)

|              | Wi-Fi 5  | Wi-Fi 6  | Wi-Fi 7  |
| -----------  | -------- | -------- | -------- |
| Versión IEEE | 802.11ac | 802.11ax | 802.11be |
| Tasa de datos máxima | 3.5 Gbps | 6.9Gbps | 40Gbps |
| Banda(s) | 5 GHz | 2.4Ghz, 5GHz,6GHz | 2.4Ghz, 5GHz, 6GHz |
| Ancho de Banda | 160 MHz por canal | 160 MHz por canal | 320 MHz por canal |
| Modulación | 256 QAM | 1024 QAM | 4096 QAM |
| Sistema de Seguridad | WPA2 | WPA3 | WPA3 |

## 2) 

### a)

La imagen ilustra transmisiones por fibra óptica monomodo y multimodo:
La transmisión por fibra monomodo transporta luz en un único modo, longitudinal, a través de la fibra, por lo tanto, no presenta dispersión modal, lo que le otorga mejores características para conexiones de alta fidelidad sobre largas distancias y obtener gran ancho de banda. Son más costosas de instalar debido al equipamiento especializado y precisión requerida.
La transmisión multimodo, por otro lado, utiliza un núcleo de fibra óptica de mayor diámetro de sección transversal, lo que permite transmitir múltiples trayectorias de luz de manera simultánea. Son más fáciles de instalar y pueden utilizar fuentes de luz más simples como LEDs en lugar de lasers, lo que abarata costos y las hace ideales para instalaciones de distancias cortas con grandes tasas de transmisión.

### b)

la ley de Snell describe el comportamiento de los rayos de luz al ser refractados cuando atraviesan la superficie de separación entre dos medios de propagación con índices de refracción diferentes. Se relaciona con las transmisiones por fibra óptica ya que permite calcular el ángulo crítico para conseguir reflexión interna total, lo que es fundamental para transmisiones multimodo en la que los distintos modos no siguen una trayectoria recta sino que se reflejan sobre el revestimiento de la misma múltiples veces. Si la reflexión es total, la señal de luz presenta pérdidas mínimas y disminuye la atenuación de la misma.

### c)

Tanto las conexiones inalámbricas como las de fibra óptica utilizan ondas del espectro electromagnético para transmitir información. Sin embargo las conexiones por fibra permiten el envío de datos a gran velocidad sobre largas distancias, lo que las hace ideales para la infraestructura principal de las redes, y aprovechar la movilidad y facilidad de instalación de las redes inalámbricas para la conexión a los dispositivos finales.

## 3)

| Protocolo  | ¿Está estandarizado? Si/No | Si aplica: ¿Cuál(es) estándares? (si tiene varios mencionar la última versión) |
| -----------  | -------- | -------- |
| Wi-Fi  | Si | IEEE 802.11be |
| Bluetooth  | Si | Bluetooth 6.1 |
| ZigBee  | Si | IEEE 802.15.4 |
| NFC  | Si | ISO 18092 |
| LTE  | Si | 3gpp Release 20 |
| GSM  | Si | TS.25 v8.0 |
| 5G (3GPP)  | Si | 3gpp Release 20 |
| LoRa  | Parcialmente | LoRa PHY propietario de Semtech / LoRaWAN por LoRa Alliance |
| NB-IoT  | Si | 3gpp Release 13 |
| SigFox  | No | -------- |
| Z-Wave  | Si | ITU-T G.9959 |

### b)

<img width="870" height="457" alt="image" src="https://github.com/user-attachments/assets/124bac05-4a55-4f50-a9d4-1fc252cc6aa0" />

Imagen 3.1

### c) 

| Característica | UTP | Fibra Óptica | Wi-Fi 802.11be | Bluetooth 5.4 | 5G |
| ----------- | -------- | -------- | ----------- | -------- | -------- |
| Ancho de banda | 100MHz (Cat5e) 1 Gbps | 100 Gbps | 320 MHz 40Gbps | 2 Mbps (LE) 50 Mbps (EDR) | 100 MHz (FR1) 400 MHz (FR2) |
| Distancias | 100 metros | 100Km (monomodal) | 5-50 metros (dependiendo banda) | Hasta 240 metros en exteriores | 100 metros - 10 Km dependiendo banda |
| Inmunidad a EMI / RFI | No | Si | No | No | No |
| Costos de medios/conector es/dispositivos | Bajo | Medio para conexiones. Alto para dispositivos monomodo | Alto para dispositivos. No requiere cableado | Bajo. No requiere cableado | Alto. No requiere cableado |
| ¿Disponible en Packet Tracer? | Si | Si | No | No | No |

## 4)

El término "Estado del Arte" se refiere al nivel de desarrollo más avanzado en una tecnología, técnica o campo de investigación en un momento dado. Es decir, lo más moderno y puntero que existe hoy en día en ese contexto.

### a)

La conexión a internet en vuelo es posible gracias a estas tecnologías.

- **Aire-Tierra (ATG o DA2GC):** Consiste en utilizar antenas colocadas en tierra, para comunicarse con las aeronaves. Pudiendo tener conexiones de hasta aproximadamente unos 100Mbps con una latencia menor a 50ms. Tiene varias ventajas, la principal es la de soportar un alto ancho de banda,  pero la desventaja es que solo funciona cuando se está sobrevolando tierra y no en océanos.

<img width="617" height="336" alt="image" src="https://github.com/user-attachments/assets/fc900d01-1d17-41c1-99b3-9df1435e37d1" />

Imagen 4.1

- **Satélites Geoestacionarios:** Un satélite geoestacionario es aquel que orbita la tierra a una distancia aproximada de 36000 km de manera que su movimiento se coordina con la rotación de la tierra, quedando siempre en el mismo punto en el cielo, esto permite apuntar hacia él para poder tener una conexión a internet, la ventaja de este método es la disponibilidad en cualquier lugar, aunque sea en el medio del océano. La desventaja es la cantidad de ancho de banda soportado el cual ronda unos  1-5 Mbps (por aeronave) y su latencia elevada >1000ms.

En vista de estas dos metodologías aproximadamente hasta 2021, algunas aerolíneas estuvieron utilizando un sistema híbrido.

A partir de 2021, los **satélites no geoestacionarios** comenzaron a tener mucha relevancia, ya que es el camino que se está utilizando actualmente, es el estado del arte del acceso a internet en aeronaves. 
Los satélites no geoestacionarios,  o LEO (Low Earth Orbit) son aquellos que orbitan normalmente entre unos 160 km y 2000 km de altura. Tienen periodos de 90 minutos aproximadamente (en dar la vuelta a la tierra) y como están bajos, no ven todo el planeta, por lo que se necesitan constelaciones de muchos satélites para cubrir globalmente.

La comunicación con estos satélites permite manejar un altísimo ancho de banda rondando entre 150 y 220 Mbps, y esto manteniendo una latencia de 25 y 70 ms lo que es más que aceptable para un acceso a internet cómodo para los pasajeros. Lo más importante es que logra registrar esas marcas sin comprometer la cobertura pudiendo utilizarse sin problemas en océanos o en los polos. La principal desventaja son las constelaciones necesarias mencionadas anteriormente. 
Empresas como StarLink, Amazon, OneWeb, Telesat están trabajando en estas tecnologías, utilizando bandas Ka / Ku LEO para lograr estas conexiones.

### b)

Investigando encontramos el siguiente paper científico.

https://arxiv.org/abs/2504.07262

### **Título:**

Enabling Continuous 5G Connectivity in Aircraft through Low Earth Orbit Satellites

### **Autores:**

Raúl Parada, Victor Monzon Baeza, Carlos Horcajo Fernández de Gamboa, Rocío Serrano Camacho, y Carlos Monzo

Publicado en arXiv (versión v1): 09 de abril de 2025

En este artículo se aborda la solución al internet en vuelo a través de LEO pero utilizando una red 5G dentro del avión en lugar de una Wifi, esto puede traer ventajas como una menor degradación de la señal y una mejor gestión de la densidad masiva de usuarios. Se utilizan simulaciones con MATLAB y SIMULINK para simular el movimiento satelital y RayTracing para estimar el comportamiento dentro del avión.

Se concluye que es factible y ventajoso aprovechar las constelaciones de satélites LEO para permitir la conectividad 5G continua en las aeronaves. 

### c) 

El contenido a bordo no viaja por internet, está almacenado en servidores dentro del avión, los pasajeros se conectan a ese servidor mediante una red LAN, igual que si fuera una red doméstica con un NAS.
El tráfico de internet (navegar, redes sociales, videollamadas, mails, etc.) si sale del avión y es el que va a gestionarse mediante las tecnologías mencionadas anteriormente.
