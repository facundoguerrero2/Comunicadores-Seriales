# 1) Alcance de Redes y Virtualización
## a) Clasificación de las redes según su alcance
Las redes de computadoras se clasifican principalmente según el área geográfica que cubren.
Principalmente son 4, PAN, LAN, MAN, WAN, desde el alcance más corto al más largo. 

* **PAN** (Personal Area Network):
Es una red de muy corto alcance (pocos metros), centrada en una sola persona. Se utiliza para conectar dispositivos personales (celulares, auriculares, relojes inteligentes).
Tecnología común: Bluetooth, Zigbee, NFC.
* **LAN** (Local Area Network):
Cubre un área geográfica pequeña y limitada, como una casa, una oficina o un edificio. Permite compartir recursos como impresoras y archivos con alta velocidad.
Tecnología común: Ethernet (cableada), Wi-Fi (WLAN).
* **MAN** (Metropolitan Area Network):
Conecta diversas LANs en un área geográfica del tamaño de una ciudad o municipio. Es el paso intermedio entre LAN y WAN.
Tecnología común: Fibra óptica urbana, redes de televisión por cable.
* **WAN** (Wide Area Network):
Cubre áreas geográficas extensas (países o continentes). Conecta múltiples redes más pequeñas (LANs y MANs). Internet es el WAN más grande.
Tecnología común: Satelital, fibra óptica submarina, 4G/5G, MPLS.


## b) Qué es una VLAN y cómo se clasifican
Una **VLAN** (Virtual Local Area Network) es una red de área local (LAN) virtual. Es una tecnología que permite crear redes lógicas independientes dentro de una misma red física. Esto permite agrupar equipos según su función o departamento (por ejemplo separar Ventas de Recursos Humanos), independientemente de dónde estén conectados físicamente, mejorando la seguridad y reduciendo el tráfico de broadcast.

#### Clasificación (Métodos de asignación):
Existen varias formas de asignar un dispositivo a una VLAN:
* **VLAN basada en Puertos (Nivel 1 - La más común):** Se configura el switch para que ciertos puertos físicos pertenezcan a una VLAN específica (ej. Puertos 1-5 son VLAN 10).
* **VLAN basada en direcciones MAC (Nivel 2):** La pertenencia a la VLAN depende de la dirección física (MAC) del dispositivo. Si se mueve la PC a otro puerto, sigue en su VLAN correspondiente.
* **VLAN basada en Protocolo o Red (Nivel 3):** Se basa en el tipo de protocolo (IP, IPX) o en la dirección de subred IP.
VLAN basada en Aplicación: Se asigna según la aplicación que se esté ejecutando (no es muy común hoy en día).

## c) Protocolo IEEE 802.1Q y su relación con las VLAN 
 El estándar IEEE 802.1Q (comúnmente llamado "Dot1q") es el protocolo industrial estandarizado para el manejo de VLANs en redes Ethernet.
 Modifica la trama Ethernet original insertando un campo adicional de 4 bytes (la etiqueta o tag) entre la dirección MAC de origen y el campo de tipo/longitud (EtherType). Esta etiqueta contiene el VLAN ID (VID), que identifica a qué VLAN pertenece esa trama.
Relación con VLAN
 Sin el protocolo 802.1Q, las VLANs estarían confinadas a un solo switch. El 802.1Q permite el Trunking (Enlace Troncal) que es la capacidad de enviar tráfico de múltiples VLANs a través de un solo cable físico entre switches o routers. Gracias a este protocolo, el switch receptor sabe a qué VLAN virtual debe entregar los datos.

## d) Tagging
El Tagging (etiquetado) es el proceso técnico de insertar la información de la VLAN en la trama de datos.
Existen dos estados fundamentales para los puertos:
Untagged (Sin etiqueta - Puerto de Acceso):
Es el puerto donde se conecta una PC o impresora.
El dispositivo final no entiende de VLANs. El switch le envía la trama limpia (sin etiqueta).
Cuando la PC envía datos al switch, el switch "marca" (tag) esos datos internamente según la configuración del puerto.
Tagged (Etiquetado - Puerto Troncal):
Es el puerto que conecta dos switches entre sí.
En este lugar es donde ocurre el Tagging. Las tramas viajan con la "etiqueta" 802.1Q pegada para que el otro switch sepa: "Esta trama es de la VLAN 10" o "Esta es de la VLAN 20".
Existe una excepción llamada VLAN Nativa. En un enlace troncal (Tagged), las tramas de la VLAN Nativa viajan sin etiqueta (untagged) por razones de compatibilidad.

# 2) 

## a) 

<img width="702" height="306" alt="imagen" src="https://github.com/user-attachments/assets/bf5b46fa-8c43-4674-99a1-92675a99f979" />

_Imagen 2.0.1_


## b) 

<img width="758" height="327" alt="imagen" src="https://github.com/user-attachments/assets/e9dc3039-d114-4b74-8ea9-4c22688b6886" />

_Imagen 2.0.2_

<img width="717" height="295" alt="imagen" src="https://github.com/user-attachments/assets/2e999931-a8fe-47c0-a5d0-93b23d93dd7b" />

_Imagen 2.0.3_


## c) 

<img width="642" height="278" alt="imagen" src="https://github.com/user-attachments/assets/69175b2a-ef50-4c54-b170-03e27a6fc3de" />

_Imagen 2.0.4_

## d) 

<img width="856" height="327" alt="imagen" src="https://github.com/user-attachments/assets/1e9fc9d0-f373-434b-ac3c-0c4503460680" />

_Imagen 2.0.5_

## e) 

<img width="703" height="432" alt="imagen" src="https://github.com/user-attachments/assets/b5fab948-3bf5-4457-962c-a01e8b0971b3" />

_Imagen 2.0.6_


## f) 


PC-A puede hacer ping a PC-B porque pertenecen a la misma VLAN y subred, y la VLAN está correctamente extendida entre ambos switches.

<img width="580" height="682" alt="imagen" src="https://github.com/user-attachments/assets/d4f57f42-bf1f-4b0b-b7e6-15b70fcf6500" />

_Imagen 2.0.7_

## h)

<img width="700" height="298" alt="imagen" src="https://github.com/user-attachments/assets/cc28c769-0624-4d4e-a69b-9ad6929e54ce" />

_Imagen 2.0.8_


## i) 
La vlan utilizada por defecto es la Vlan 1.

<img width="934" height="373" alt="imagen" src="https://github.com/user-attachments/assets/a6468cc9-2c7b-4a0e-91d3-db17adf5f09f" />

_Imagen 2.0.9_


## j,k. l)

<img width="674" height="770" alt="imagen" src="https://github.com/user-attachments/assets/f5c2819c-2c1b-4e93-8e12-a3f1349c56bf" />

_Imagen 2.1.0_



Al verificar las VLAN con show vlan brief se observa que VLAN 10 está asignada correctamente al puerto donde se conecta PC-A, mientras que VLAN 99 existe pero no tiene puertos asignados, ya que será utilizada únicamente como VLAN de gestión.
En show ip interface brief se verifica que la interfaz VLAN 99 tiene la IP asignada, pero su estado de protocolo está DOWN. Esto ocurre porque la VLAN 99 no tiene puertos activos asociados ni está siendo transportada correctamente por el enlace hacia el otro switch.

## n) 
En este punto, las PCs fueron asignadas a la VLAN 10, pero el enlace entre los switches quedó configurado en otra VLAN (VLAN 1).

Debido a esto, la VLAN 10 no se extiende entre SW1 y SW2, quedando separada en cada switch.
Como consecuencia, aunque PC-A y PC-B pertenezcan a la misma subred IP, no pueden comunicarse entre sí.

<img width="557" height="487" alt="imagen" src="https://github.com/user-attachments/assets/0bf167dc-2aa5-4f2f-a773-f27040ae3c71" />

_Imagen 2.1.1_


<img width="692" height="322" alt="imagen" src="https://github.com/user-attachments/assets/454918fd-6e57-40bc-80db-4c06955079dc" />

_Imagen 2.1.2_







## 3) 

La red se implementó utilizando una topología **_Router-on-a-Stick_**, como se ve en el diagrama de Packet Tracer. Esta arquitectura se eligió por su eficiencia, ya que permite gestionar múltiples VLANs a través de una única interfaz física del router.

<img width="904" height="490" alt="imagen" src="https://github.com/user-attachments/assets/017e9ea3-6f5d-4456-8a8e-ffba68f20eee" />

_Imagen 3.0.1_


**Los componentes principales son:**

* **Un Switch central (Switch0):** Al cual se conectan todos los dispositivos finales de la red interna, incluyendo el servidor de entretenimiento (Server0) y las terminales de Turista, Business y Admin . 

* **Segmentación lógica con VLANs:** El switch se configuró para separar el tráfico en tres redes aisladas:
    * VLAN 10 (Turista) 
    * VLAN 20 (Business)
    * VLAN 99 (Administración) 
* **Un Router (Router1):** Se conecta al switch mediante un enlace troncal (trunk) que transporta el tráfico de todas las VLANs . El router utiliza subinterfaces (una para cada VLAN) para permitir (o denegar) la comunicación entre ellas . 
* **Servidor de Entretenimiento (Server0):** Contiene las películas que cualquier pasajero puede acceder 
* **Simulación de Internet:** Se utilizó un segundo router (Internet) y un servidor (Server3) para simular la red externa del ISP , permitiendo probar la conectividad a Internet (8.8.8.8)


**Siguiendo esta tabla de direccionamiento**

<img width="883" height="251" alt="imagen" src="https://github.com/user-attachments/assets/dce7bfcb-97dd-47aa-ac33-f38b2e763db0" />

_Tabla 3.0.1_

**Ipconfig pc Turista**

<img width="837" height="379" alt="imagen" src="https://github.com/user-attachments/assets/e87b4dff-2b16-4e68-b666-21a8cb17da20" />

_Imagen 3.0.2_

**Ipconfig pc Business**

<img width="910" height="387" alt="imagen" src="https://github.com/user-attachments/assets/9f3014a7-8865-4225-acb0-4fb73bf9dc56" />

_Imagen 3.0.3_

**Config Admin**

<img width="908" height="387" alt="imagen" src="https://github.com/user-attachments/assets/e068572b-6924-485d-8189-4608f79a1e11" />

_Imagen 3.0.4_

**Vlan brief (Switch)**

<img width="941" height="307" alt="imagen" src="https://github.com/user-attachments/assets/b3cb5b17-8fcf-4f24-ab20-1c6cd5a8cf9b" />

_Imagen 3.0.5_

Una vez configurado pasamos a las pruebas donde se deberá seguir el acceso según la tabla donde las personas de **turista** solamente podrían tener acceso al **Server** de entretenimiento, las personas de **business** deberían tener acceso al Server y a **Internet**, mientras que el **administrador** debe tener acceso **total**.


### PRUEBAS DESDE TURISTA




#### PINGS DESDE TURISTA

<img width="727" height="695" alt="imagen" src="https://github.com/user-attachments/assets/da82f27b-da68-4762-b010-61b095f55a01" />

_Imagen 3.0.6_



#### TURISTA CARGA DE PÁGINA

<img width="727" height="348" alt="imagen" src="https://github.com/user-attachments/assets/7fe1b5a9-0e65-4619-ac80-d6c729f4cf48" />

_Imagen 3.0.7_


### PRUEBAS DESDE BUSINESS

#### PINGS DESDE BUSINESS

<img width="780" height="772" alt="imagen" src="https://github.com/user-attachments/assets/848bca51-4a07-4189-8d18-ee05c7c557cb" />

_Imagen 3.0.8_


#### BUSINESS CARGA DE PÁGINA 

<img width="789" height="374" alt="imagen" src="https://github.com/user-attachments/assets/2e0590c9-28cc-48b1-85e6-beb15f66b9ef" />

_Imagen 3.0.9_


### PRUEBAS DESDE ADMIN 

#### PINGS DESDE ADMIN

<img width="563" height="760" alt="imagen" src="https://github.com/user-attachments/assets/d007bd09-77fc-46b1-9fb1-468c509aa6b8" />

_Imagen 3.1.0_

#### ADMIN CARGA PAGINA 

<img width="617" height="290" alt="imagen" src="https://github.com/user-attachments/assets/b221c893-4c1e-4312-9a11-c97137fef77f" />

_Imagen 3.1.1_


De esta forma podemos confeccionar la siguiente tabla

<img width="442" height="406" alt="imagen" src="https://github.com/user-attachments/assets/f4d34765-7dd5-44dd-8830-1731377596c9" />

_Tabla 3.0.2_


## Conclusiones
Las VLANs son cruciales para la seguridad y la segmentación. Se demostró que es posible tener a todos los usuarios (Turista, Business, Admin) conectados al mismo hardware pero aislados lógicamente. 

El enrutamiento Router-on-a-Stick centraliza el control. Al pasar todo el tráfico entre VLANs por el Router1, este se convierte en el punto de control perfecto para aplicar políticas de seguridad.

Se configuró con éxito una ACL para cumplir el requisito de que la clase Turista solo tuviera acceso a un sistema de entretenimiento. 

Se utilizó NAT (Network Address Translation) para "traducir" las direcciones IP privadas de las VLANs de Business y Admin (redes 10.10.20.0/24 y 10.10.99.0/24) a la dirección IP pública del router, permitiéndoles navegar por Internet, tal como se verificó con los pings .


