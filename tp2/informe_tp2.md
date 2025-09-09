# Comunicaciones de Datos Laboratorio N°2

**Integrantes:**

 _Federico Cechich_

 _Facundo Guerrero_

 _Ignacio J. Vigezzi_

**Nombre del grupo**: _Comunicadores-Seriales_

**Universidad Nacional de Cordoba**

**Facultad de Ciencias Exactas, Fisicas y Naturales**

**Asignatura:** Comunicaciones de datos

**Profesores:** Facundo Oliva Cuneo y Santiago Martín Henn

**Fecha:** 07/09/2025

---

**Informacion de contacto**: _Cechich Federico - federico.cechich@mi.unc.edu.ar_
                             _Guerrero Facundo - facundo.guerrero.pozzi@mi.unc.edu.ar_
                             _Vigezzi Ignacio - ignacio.vigezzi@mi.unc.edu.ar_

## 1)

### a)

La figura muestra un emisor (el barco) que envía ondas y un receptor (el satélite) situado delante: las ondas están comprimidas en la dirección del receptor (crestas más próximas). Esto representa el efecto Doppler, el cambio en la frecuencia (y longitud de onda) observada cuando hay movimiento relativo entre la fuente y el observador.

Las características principales son: 

- **Cambio de frecuencia percibida.** Si la fuente y el observador se aproximan, la frecuencia observada aumenta . Si se alejan, la frecuencia observada disminuye.


- **Cambio de longitud de onda.** Cuando se aproximan, la longitud de onda en la dirección del movimiento se acorta; cuando se alejan, se alarga.


- **Depende de la velocidad relativa.** La magnitud del corrimiento depende de la velocidad relativa: para ondas mecánicas se mide respecto al medio (p. ej. aire) y para ondas electromagnéticas se aplica respecto a un marco de referencia (sistema de coordenadas y relojes), usando la fórmula relativista cuando las velocidades son altas.


### b)

El desplazamiento en Hz crece proporcionalmente con la frecuencia de la portadora fc.

- Más afectadas: SHF y EHF (p. ej. 5–60 GHz y superiores). A la misma velocidad relativa producen desplazamientos absolutos en Hz mucho mayores (requieren tracking/compensación rápida).

- Menos afectadas: HF, VHF y parte de UHF. El desplazamiento absoluto en Hz es menor y por tanto es más fácil de compensar con PLLs, estimación de portadora y técnicas convencionales.

### c)

Por precaución, las autoridades aeronáuticas recomiendan apagar o activar el modo avión en los teléfonos porque las emisiones de los dispositivos portátiles podrían, en ciertos casos, introducir ruido o interferencias en los sistemas de comunicaciones y navegación de la aeronave; por ello la FAA y otras agencias mantienen directrices que obligan al operador a evaluar y autorizar el uso a bordo.

A la velocidad y altitud de un avión el desplazamiento de frecuencia (Doppler) sobre las portadoras celulares y Wi-Fi no es despreciable y complica la operación normal de una red diseñada para usuarios en tierra. En términos prácticos, sistemas como LTE/5G y protocolos de handover funcionan bien hasta ciertos desplazamientos; por encima de ciertos valores (orden de 1 kHz en muchas condiciones) el rendimiento se degrada y aumentan problemas de sincronía y errores.

Por eso, aunque el riesgo de interferir con la aviónica es bajo con la tecnología actual, uno de los principales problemas prácticos es que los móviles en vuelo afectan la operación normal de las redes celulares en tierra.

---

## 2)

### a)

La figura representa un pulso de interferencia electromagnética (ruido impulsivo) superpuesto a una señal transmitida, generado por una fuente electromecánica (herramienta, conmutación eléctrica, etc.). Aparece como una ráfaga breve con amplio contenido en alta frecuencia, de carácter no periódico y amplitud relativamente alta, que distorsiona la transmisión.

### b)

- Más afectadas:
  - HF / VLF y parte de VHF (bajas frecuencias): el ruido impulsivo (industrial, chispas, motores, líneas eléctricas) concentra energía en bandas bajas, generando más interferencias y ruido de fondo.

  - Sistemas simples (umbral/sensores): un pulso dentro de la banda rompe la señal y produce falsos disparos.

- Más resilientes:
  - Enlaces digitales de banda ancha (OFDM, LTE, Wi-Fi): los errores aparecen en ráfagas que se corrigen con codificación e interleaving.

  - Fibra óptica: inmune al EMI (Electromagnetic Interference) y al ruido impulsivo, ya que la transmisión se realiza por luz en el núcleo, sin acoplar campos eléctricos/magnéticos externos.

### c)

La SNR (Signal-to-Noise Ratio) es la relación entre la potencia de la señal útil y la potencia del ruido en el canal, y se expresa en decibelios (dB). Un valor alto de SNR indica una señal claramente distinguible del ruido, lo que mejora la calidad de transmisión.

La BER (Bit Error Rate) mide la proporción de bits erróneos recibidos respecto al total transmitido. Existe una relación directa entre ambos conceptos: a mayor SNR, menor BER, y viceversa. Por lo tanto, la SNR es un parámetro clave que determina la probabilidad de error en un sistema de comunicaciones.

---

## 3)

El Ethernet es una tecnología de red de área local (LAN) que se utiliza para conectar dispositivos en una red. Permite que computadoras, impresoras y otros dispositivos se comuniquen entre sí a través de cables, como el cable Ethernet (RJ45). Es el estándar más común para redes cableadas en hogares y oficinas. Define las características de cableado y señalización de nivel físico y los formatos de tramas de datos del nivel de enlace de datos del modelo OSI.

### Principales características de Ethernet

**Conexión por cable**
Ethernet es una tecnología de red cableada. A diferencia del Wi-Fi, requiere un cable físico (generalmente un cable de par trenzado con conectores RJ45) para conectar dispositivos entre sí. Esto proporciona una conexión más estable y menos propensa a interferencias que las redes inalámbricas.

**Velocidad y Estándares**
La velocidad de Ethernet ha evolucionado enormemente a lo largo de los años. Se conocen distintas categorías, como Ethernet, Fast Ethernet, Gigabit Ethernet donde la diferencia se encuentra en la velocidad de transferencia de datos.

* Ethernet: 10 Mbps
* Fast Ethernet: 100 Mbps
* Gigabit Ethernet: 1 Gbps (1000 Mbps). Este es el estándar más común en la mayoría de los hogares y oficinas hoy en día.
* 10 Gigabit Ethernet (10 GbE): 10 Gbps. Se usa en entornos que requieren altas velocidades, como centros de datos.

Cada velocidad está asociada a diferentes categorías de cables (Cat5e, Cat6, Cat7, etc.), que están diseñadas para manejar esas velocidades y anchos de banda.

**Transferencia de datos en tramas**
Ethernet divide la información en pequeños paquetes de datos llamados tramas.

Cada trama contiene la dirección de origen y destino de los dispositivos, lo que permite que la información sea enviada de manera ordenada y eficiente a través de la red. Además, utiliza un mecanismo para detectar y corregir errores en la transmisión, garantizando que los datos lleguen intactos.

**Definición de tramas:**


_Imagen 3.1_
* Preámbulo:  Secuencia de 7 bytes (56 bits) de unos y ceros alternados. Advierte al receptor que la transmisión está a punto de comenzar.
* Dirección Destino (DD): Dirección MAC del receptor.
* Dirección Origen (DO): Dirección MAC del emisor.
* Tipo: Indica el protocolo de la capa superior que envió los datos.
* Data: Información real a enviar.
* FCS (Frame Check Sequence): Para detección de errores.

**Topología en estrella**
Las redes Ethernet casi siempre se organizan en una topología en estrella. Todos los dispositivos se conectan a un punto central (switch o router). Si un cable falla, solo se desconecta un dispositivo, sin afectar al resto.

**Dirección MAC única**
Cada dispositivo tiene una dirección MAC única de 48 bits (6 bytes) asignada por el fabricante, lo que garantiza unicidad a nivel mundial.

### b) 
Un cable UTP (Unshielded Twisted Pair) es el más utilizado en Ethernet. Su diseño trenzado cancela interferencias externas mediante transmisión diferencial y rechazo de modo común.


_Imagen 3.2_

Su relación con el punto 2 de este trabajo radica en su construcción, la cual está pensada para mitigar las interferencias (ruido). Los cables UTP consisten en pares de hilos de cobre que están entrelazados entre sí. 

Cuando una señal eléctrica viaja por un cable, genera un campo electromagnético. Ese campo puede recibir interferencia de fuentes externas (motores, radio, etc).

Ethernet no manda una señal por un solo cable, manda la señal como diferencia entre los dos hilos del par (lo que se llama señal balanceada o diferencial). Al ser trenzado, si hay ruido externo, se mete con la misma polaridad en los dos hilos. El receptor solo lee la diferencia entre los dos, el ruido común se cancela. Esto se llama rechazo de modo común.

Este diseño está directamente ligado a las características de velocidad y fiabilidad de Ethernet. Al minimizar la interferencia, el cable puede transmitir datos a velocidades más altas y de forma más estable, lo que es crucial para los estándares como Gigabit Ethernet.

**Diferencias entre cable UTP derecho y cruzado:**

La diferencia entre los cables UTP derechos y los cruzados está en que dispositivos vamos a conectar.

* Cable derecho (straight-through):

  Los pines se conectan de la misma forma en ambos extremos.
  Se usa para conectar dispositivos diferentes: PC ↔ switch, router ↔ PC, etc.
  Ejemplo: pin 1 va a pin 1, pin 2 a pin 2, etc.
* Cable cruzado (crossover):

  En un extremo los pares de transmisión y recepción están intercambiados.
  Se usa para conectar dispositivos del mismo tipo directamente: PC ↔ PC, switch ↔ switch.


Aunque hoy muchos equipos ya hacen ese cruce de forma automática con Auto-MDI/MDIX.

Los pinout están definidos por standards de cableado como  T568A y T568B.


_Imagen 3.3_

### c)

La puerta de enlace predeterminada de la conexión es: 192.168.0.1.

_Imagen 3.4_

Se envió un ping a la puerta de enlace y se analizaron los paquetes en Wireshark con filtro `ip.addr == 192.168.0.1`. 

_Imagen 3.5_

_Imagen 3.6_

En esta imagen podemos observar datos como:

* Número de paquete: 11721
* Time: Tiempo transcurrido desde que se empezaron a capturar los paquetes hasta ese paquete en específico 386.15 [segundos].

* Source:  IP origen 192.168.0.5. En este caso la de la PC de escritorio.
* Destination: IP Destination 192.168.0.1. En este caso la ip del gateway.
* Protocolo: Protocolo de red que se utiliza en el paquete. En este caso, el protocolo es ICMP.

* Length: Indica el tamaño del paquete de red en bytes 98 en este caso.
* Info: Resumen descriptivo del paquete


Al hacer doble clic sobre el paquete se nos abre la siguiente ventana.

_Imagen 3.7_

De donde se puede obtener la siguiente información.



```
0000   f4 6b ef d5 2a bc e0 d5 5e 8b bb e5 08 00 45 00
0010   00 54 f6 b5 40 00 40 01 c2 9c c0 a8 00 05 c0 a8
0020   00 01 08 00 94 3b 25 3d 00 20 e3 9c b9 68 00 00
0030   00 00 dd 8e 05 00 00 00 00 00 10 11 12 13 14 15
0040   16 17 18 19 1a 1b 1c 1d 1e 1f 20 21 22 23 24 25
0050   26 27 28 29 2a 2b 2c 2d 2e 2f 30 31 32 33 34 35
0060   36 37
```


| Campo           | Valor en Hexadecimal | Valor Interpretado   |
| --------------- | -------------------- | -------------------- |
| **MAC Origen**  | `e0 d5 5e 8b bb e5`  | e0\:d5:5e:8b\:bb\:e5 |
| **MAC Destino** | `f4 6b ef d5 2a bc`  | f4:6b\:ef\:d5:2a\:bc |
| **IP Origen**   | `c0 a8 00 05`        | 192.168.0.5          |
| **IP Destino**  | `c0 a8 00 01`        | 192.168.0.1          |

De esta manera se puede observar tanto la capa de **Enlace (Ethernet)** como la de **Red (IP)** a partir de la trama capturada.


### d)


_Imagen 3.8_

Con la herramienta online analizamos la dirección MAC de la PC de origen y podemos ver datos como el fabricante Giga-Byte, el país de fabricación Taiwán, la fecha de fabricación 20/2/2017, y si está o no registrado, en este caso True lo que asegura que tiene una dirección MAC única a nivel mundial, evitando conflictos con otros fabricantes.
 Como dato la motherboard de esta pc es una GIGABYTE A320M-S2H, con su placa de red integrada (no externa) lo cual claramente coincide con el fabricante indicado en la página.


### e)

Repetimos los pasos pero en lugar de trackear al gateway lo hacemos hacia una notebook con windows conectada a la misma red.


_Imagen 3.9 (ipconfig windows)_

Podemos ver la dirección IP de la notebook.


Hacemos ping hacia esa ip.  

_Imagen 3.10_

Vemos los paquetes capturados en wireshark.

_Imagen 3.11_

Datos del paquete 1669.

_Imagen 3.12_

```
0000   38 d5 7a 58 22 ff e0 d5 5e 8b bb e5 08 00 45 00
0010   00 54 e8 b6 40 00 40 01 d0 91 c0 a8 00 05 c0 a8
0020   00 0b 08 00 78 55 18 4a 00 04 f7 20 ba 68 00 00
0030   00 00 e9 ff 0d 00 00 00 00 00 10 11 12 13 14 15
0040   16 17 18 19 1a 1b 1c 1d 1e 1f 20 21 22 23 24 25
0050   26 27 28 29 2a 2b 2c 2d 2e 2f 30 31 32 33 34 35
0060   36 37

```


Nos fijamos ahora la MAC receptora (ya que elegimos un paquete donde la notebook esta recibiendo). 

**38 d5 7a 58 22 ff**

_Imagen 3.13_

En la herramienta online podemos ver que se fabrico el 27/4/21 en Canada y fue fabricada por Cloud Network Tech Singapore Pte. Ltd.

La notebook es de la marca DELL y al parecer Dell no fabrica sus propias notebooks, sino que terceriza la producción, uno de sus principales fabricantes es Foxconn que es una empresa taiwanesa, y Cloud Network Technology Singapore es una de las tantas filiales de Foxconn

## 4) 

En este trabajo comprobamos experimentalmente cómo las tramas Ethernet contienen direcciones MAC origen y destino, permitiendo a los dispositivos de la red local identificar al emisor y receptor. Esa propiedad hace que la dirección MAC sea trazable dentro del segmento de red y útil para identificar el fabricante mediante el OUI. No obstante, las plataformas modernas incorporan técnicas de privacidad (MAC randomization) que dificultan el seguimiento entre redes, aunque existen métodos que pueden debilitar esa protección. 

En redes globales la dirección MAC no es visible en el extremo remoto, la MAC sólo existe y se usa en cada enlace local, y los routers reemplazan las MAC en cada salto. Por tanto, al enviar datos a un servidor en otra red, este servidor no recibe la MAC de nuestro equipo sino la MAC del último salto de enlace (por ejemplo la de su router/switch). Esto implica que la trazabilidad con MACs está limitada al ámbito local y a los dispositivos de infraestructura cercanos.

El IMEI es un identificador único del equipo móvil utilizado por las redes celulares durante el registro y en la señalización de la red (procedimientos de autenticación, gestión de roaming, listas negras por robo, etc.). A diferencia de la dirección MAC, que existe en las tramas de enlace de una LAN, el IMEI se intercambia en mensajes de control entre el dispositivo celular y el operador móvil y no se incluye en las tramas Ethernet/IP que llega a un servidor remoto en Internet. Por eso, servidores externos no pueden ver el IMEI, si lo pueden ver y registrar los operadores móviles y sistemas que tienen acceso a la señalización de la red.

Finalmente, una VPN no oculta la dirección MAC frente a la infraestructura local. Su misión es cifrar y ocultar el tráfico IP hacia el exterior, por lo que para proteger la privacidad a distintos niveles es necesario combinar buenas prácticas (randomización de MAC, uso correcto de VPN, y configuración de la red). 
