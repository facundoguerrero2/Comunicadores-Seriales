# Comunicaciones de Datos Laboratorio N°5

**Integrantes:**

 _Federico Cechich_

 _Facundo Guerrero_

 _Ignacio J. Vigezzi_

**Nombre del grupo**: _Comunicadores-Seriales_

**Universidad Nacional de Cordoba**

**Facultad de Ciencias Exactas, Fisicas y Naturales**

**Asignatura:** Comunicaciones de datos

**Profesores:** Facundo Oliva Cuneo y Santiago Martín Henn

**Fecha:** 21/11/2025

---

**Informacion de contacto**: _Cechich Federico - federico.cechich@mi.unc.edu.ar_
                             _Guerrero Facundo - facundo.guerrero.pozzi@mi.unc.edu.ar_
                             _Vigezzi Ignacio - ignacio.vigezzi@mi.unc.edu.ar_


# 1) 
## MQTT
 MQTT es un protocolo de mensajería estándar basado en TCP/IP para el Internet de las Cosas (IoT). Está diseñado como un sistema de mensajería publish/subscribe extremadamente liviano, es ideal para conectar dispositivos remotos que necesitan poco código y muy poco ancho de banda. Hoy en día se usa en muchas industrias, como la automotriz, las telecomunicaciones, el petróleo y el gas.

**Características Principales:**
* **Modelo Pub/Sub:** No hay conexión directa entre cliente y servidor como en HTTP, hay publicadores, suscriptores y un intermediario (broker).
* **Ligero** La cabecera del paquete es muy pequeña 
    QoS (Calidad de Servicio): Ofrece tres niveles de garantía de entrega 0, 1 y 2
* **Retención de Mensajes:** El broker puede guardar el último mensaje de un tópico para nuevos suscriptores.
* **Last Will and Testament:** Permite notificar a otros clientes si un dispositivo se desconecta inesperadamente.

**Ventajas:**

* **Desacoplamiento:** Los dispositivos no necesitan conocerse entre sí, sólo conocer al Broker.
* **Eficiencia:** Consume muy poca batería y datos
* **Escalabilidad:** Permite conectar miles de dispositivos a un solo Broker.
* **Fiabilidad:** Los niveles de QoS aseguran la entrega incluso en redes con interrupciones.

**Desventajas:**
* **Punto único de fallo:** Si el Broker central cae, toda la red deja de comunicarse.
* **Seguridad:** Por defecto no cifra los datos; requiere implementación adicional.
* **Latencia:** En escenarios de tiempo real crítico, el paso por el Broker puede añadir una latencia mayor que una conexión directa socket-to-socket.

**Principales Usos:**
* **Domótica:** Sensores de temperatura, luces inteligentes, termostatos.
    Telemetría Industrial: Monitoreo de maquinaria en fábricas.
    Logística: Rastreo de activos y flotas de vehículos.
* **Aplicaciones de Chat:** Facebook Messenger, por ejemplo, ha utilizado MQTT para chats móviles por su bajo consumo.


El patrón de diseño **PubSub**, es una estrategia de diseño de comunicación asíncrona en donde se tienen **publicadores** (emisores del mensaje), **suscriptores** (receptores del mensaje), y un **intermediario** (broker). 
 Los publicadores envían mensajes, no lo hacen hacia un suscriptor en particular, el broker recibe estos mensajes, los filtra y envía a los suscriptores correspondientes, los  cuales están “suscritos” a ese tópico.

# 2) 3)

<img width="947" height="428" alt="imagen" src="https://github.com/user-attachments/assets/90ed245e-dfd5-4b4c-bae2-d3680a1a4526" />

_Imagen 1.1_

Cliente y Broker MQTT mediante mosquitto en linux, el terminal de la derecha publica mensajes en lan/devices/status y el terminal de la izquierda muestra el cliente suscrito que los recibe.

# 4)

<img width="949" height="430" alt="imagen" src="https://github.com/user-attachments/assets/b0f7b38e-c44f-4be7-b7a9-d5c8122456b5" />


_Imagen 1.2_

Simulación de broadcasting con cliente central que publica mensajes en un tópico general lan/broadcast/all, con dos clientes suscritos.


# 5)

<img width="948" height="503" alt="imagen" src="https://github.com/user-attachments/assets/8c14ad85-4989-4901-87b1-22a526b6fcc6" />

_Imagen 1.3_

Mediante scripts de python y mosquitto se simula una serie de sensores que generan datos y los publican, con un cliente central que se suscribe y recibe los datos de todos los sensores 

<img width="949" height="503" alt="imagen" src="https://github.com/user-attachments/assets/1c3db1db-fee5-4bfe-8dd3-9e206a350ff9" />

_Imagen 1.4_

<img width="837" height="443" alt="imagen" src="https://github.com/user-attachments/assets/675e433c-c2d3-48d0-bcbf-7671820997ed" />

_Imagen 1.5_

<img width="836" height="446" alt="imagen" src="https://github.com/user-attachments/assets/0a3a3f46-a822-4b86-9ece-9b078b7cba7c" />


_Imagen 1.6_
Se agrega a la simulación una serie de comandos que son publicados por el cliente central o gateway que permiten iniciar o detener la toma de datos de los sensores suscritos al tópico de comandos. Estos publican los datos muestreados que el cliente central registra en archivos de texto

<img width="840" height="417" alt="imagen" src="https://github.com/user-attachments/assets/daf448d9-f9a3-45f8-8db7-02e4587271ba" />

_Imagen 1.7_

# 6)

## a)
En esta actividad se trabaja sobre el protocolo **TCP** como protocolo de transporte.
**MQTT** se implementa típicamente sobre **TCP** porque garantiza una comunicación **confiable, ordenada y sin pérdidas**, lo cual es esencial para entregar mensajes de sensores y dispositivos IoT.

Opcionalmente, algunos brokers y clientes también soportan:
* **TCP + TLS/SSL** (usando MQTT sobre puertos seguros como 8883) para comunicaciones cifradas.
* En algunos casos avanzados, existe **MQTT-SN**, que funciona sobre UDP, pero no se utiliza en esta actividad.

## b)
* **Integridad:** La integridad depende principalmente del protocolo de transporte TCP, que garantiza que los mensajes lleguen completos, sin corrupción y en el orden correcto.
* **Confidencialidad:** Por defecto, MQTT no provee confidencialidad: los mensajes viajan en texto claro sobre TCP.
* **Disponibilidad:** La arquitectura depende fuertemente del broker central. Si el broker falla o está inaccesible, toda la red queda inoperable, incluso si los dispositivos están en la misma LAN.

## c) 
Los niveles de **QoS** en MQTT determinan la garantía de entrega de los mensajes:

* **QoS 0:** entrega sin confirmación, no garantiza que el mensaje llegue.
* **QoS 1:** asegura que el mensaje llega al menos una vez, pero puede duplicarse.
* **QoS 2:** asegura que el mensaje llega exactamente una vez, sin duplicados, siendo el más confiable pero también el más costoso en tiempo y recursos.

## d) 
El modelo **publish/subscribe** ofrece varias ventajas importantes sobre el modelo cliente-servidor tradicional:

* **Desacoplamiento total:** los emisores (publishers) no necesitan conocer a los receptores (subscribers). Sólo publican en un tópico y el broker se encarga del routing.
* **Escalabilidad:** cada cliente mantiene una sola conexión con el broker. Soporta decenas, cientos o miles de dispositivos sin que crezca la complejidad.
* **Comunicación eficiente uno-a-muchos:** mediante tópicos y comodines, un mensaje puede llegar fácilmente a múltiples receptores (broadcast y multicast lógico).
* **Tolerancia a fallos:** si un cliente se desconecta, la comunicación continúa; cuando vuelve, puede recibir mensajes pendientes (según QoS).
* **Flexibilidad:** permite agregar o quitar dispositivos sin modificar el resto de la red.

 En resumen, pub/sub es más escalable, flexible y adecuado para IoT que el modelo cliente-servidor, que requiere conexiones directas y dependencias fuertes entre cada par de nodos.

## e) 
Aunque MQTT permite simular comunicaciones en una LAN, presenta varias limitaciones frente a una red local real:

* **Dependencia del broker:** toda la comunicación pasa por un único punto central. Si el broker falla, la red completa deja de funcionar (single point of failure).
* **Mayor latencia:** los dispositivos nunca se conectan entre sí; toda la interacción es indirecta a través del broker.
* **Seguridad limitada por defecto:** MQTT no cifra el tráfico ni autentica a los nodos a menos que se configure TLS, mientras que una LAN puede tener controles adicionales.
* **Limitaciones de transferencia de datos:** MQTT está pensado para mensajes pequeños y livianos. No es adecuado para enviar archivos grandes, audio, video o tráfico de alto volumen como sí puede manejar una LAN.
* **No maneja congestión ni características del medio físico:** A diferencia de una LAN física, MQTT no controla el medio físico: no gestiona colisiones, congestión ni la limitación de ancho de banda del enlace, porque opera sobre TCP/IP y depende completamente de la capa de red subyacente para esos aspectos.

## f) 
Depender de un **broker central** en MQTT da muchas ventajas (desacoplamiento, facilidad de suscripción/publicación, QoS), pero también trae riesgos importantes: un punto único de fallo, sobrecarga del broker, problemas de seguridad si no se configura bien, y dependencia de la infraestructura de red.

En sistemas críticos, lo ideal es diseñar con **redundancia** (clusters de broker) y políticas de seguridad fuertes.




