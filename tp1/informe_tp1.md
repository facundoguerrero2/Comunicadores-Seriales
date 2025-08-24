
# Comunicaciones de Datos Laboratorio N°1

**Integrantes**
_Federico Cechich_

_Facundo Guerrero_

_Ignacio J. Vigezzi_

**Nombre del grupo**:_Comunicadores-Seriales_

**Universidad Nacional de Cordoba**

**Facultad de Ciencias Exactas, Fisicas y Naturales**

**Asignatura:** Comunicaciones de datos

**Profesores:** Facundo Oliva Cuneo y Santiago Martín Henn

**Fecha:** 25/08/2025

---

**Informacion de contacto**: _Cechich Federico - federico.cechich@mi.unc.edu.ar_
                             _Guerrero Facundo - facundo.guerrero.pozzi@mi.unc.edu.ar_
                             _Vigezzi Ignacio - ignacio.vigezzi@mi.unc.edu.ar_

## Introducción
En este informe se buscara refrescar conceptos de Comunicaciones Digitales y Teoria de las Comunicaciones ademas de familiarizarse con el software Packet Tracer de Cisco Systems

## 1)
Analizando el siguiente grafico de onda electromagnética.
<img width="711" height="230" alt="image" src="https://github.com/user-attachments/assets/22909461-304e-4d1c-8c5d-b62f8071810c" />

_Figura 1.1_

### b) 
De la figura deducimos que la **longitud de onda** es de $\lambda = 60mm$.
La frecuencia está dada por:

$$c = 3x10^8 m/s$$ $$λ = 60mm$$ $$f = \frac{c}{λ}  = 5.0 GHz.$$

### c)
La frecuencia de **5 GHz** se encuentra dentro del rango de radio, específicamente en la parte de microondas, lo que corresponde a la banda denominada SHF (Super High Frequency), que abarca aproximadamente de 3 GHz a 30 GHz. 

### d)
Wi-Fi en 5 GHz, que proveen conectividad inalámbrica de alta velocidad en casas, oficinas y espacios públicos. Dispositivos como notebooks, celulares o televisores son ejemplos que operan en esta banda.

### e)
Con la linea de trazos roja se quiere representar la caída de la potencia de la señal, en espacio libre la potencia recibida es inversamente proporcional al cuadrado de la distancia.

### f)
Este fenómeno sí, afecta al Wi-Fi de 5 GHz: al aumentar la distancia, la potencia recibida disminuye notablemente. En la vida cotidiana se nota cuando la señal de Wi-Fi se debilita o se corta al alejarse del router.

### g)
* El fenómeno descrito tiene implicancia en la telefonía celular ya que también sufre pérdida de potencia con la distancia (path loss).
* No es de la misma forma en las transmisiones de cable coaxial  ya que no aplica la ley $\frac{1}{r^2}$, sino una atenuación exponencial con la longitud del cable.
* Tampoco de la misma forma en fibra óptica, donde la señal se atenúa también exponencialmente con la distancia, por absorción y dispersión en el material.


## 2)
### a)
Analizando el siguiente gráfico:
<img width="784" height="253" alt="image" src="https://github.com/user-attachments/assets/9bfa4e61-0e70-4be2-a913-a0820f13b5e5" />

_Figura 2.1_ 
#### Tipo de transmisión : 
Se puede observar una **transmisión digital, serial y síncrona** ya que se comparte el mismo clock y la información va por un único canal.

#### Modo de transmisión : 
Por lo que se observa en la imagen estamos frente a una transmisión **Simplex**, ya que va en una sola dirección.  

### b) 
Este no es el mejor paradigma si buscamos transmitir datos rápidamente y de forma bidireccional, si bien en cuanto a la **velocidad de transmisión** si es una ventaja el que estemos en un tipo de comunicación síncrona, no podemos optar por este paradigma para comunicación bidireccional ya que es Simplex (unidireccional).

### c)
En el nombre “Comunicadores-Seriales” la cuarta letra es la `u` (u minúscula), la cual corresponde a `01110101` en binario, gráficamente se vería de la siguiente manera:

<img width="579" height="163" alt="image" src="https://github.com/user-attachments/assets/9dc63904-e122-4969-ae66-e7bbabb722ef" />


_Figura 2.2_

### d)
Debido a la pendiente que hay en el cambio de niveles de tensión, lo ideal sería medir el valor de la señal cuando ese cambio de nivel ya está estabilizado (en el centro del intervalo temporal de cada bit) siguiendo lo indicado en la figura como **T0 T1 T2 T3 T4 … Tn**  Lo ideal sería medirlo en los **Tpares** es decir **T0, T2, T4, T6…** Dado que estos corresponden al centro del intervalo temporal de cada bit.


## 3) 
### Transmision inalambrica de datos y Phase Shift Keying

Transmitir una señal escalonada de manera inalambrica presenta multiples inconvenientes, entre los principales se encuentran que al haber transiciones bruscas se presentan componentes de frecuencias muy altas, provocando que la señal sea altamente susceptible al ruido, el canal pueda distorsionar la señal con gran facilidad, sea más difícil mantener la sincronización y se genere interferencia con otros sistemas de comunicación al ocupar tantas frecuencias. Para solucionar esto se utilizan tecnicas de modulación.

<img width="1225" height="427" alt="image" src="https://github.com/user-attachments/assets/5ea81e23-109f-4eed-a51a-5bea5897c57c" />

_Figura 3.1_

Un ejemplo de tecnicas de modulación es Phase-Shift Keying o PSK (ver Figura 3.1), consiste en variar la fase de la señal portadora asignandole un valor a cada simbolo que se quiere transmitir
Si quisieramos utilizar esta tecnica para transmitir la cadena de bits 01110110 la señal transmitida tendria la sigiente forma:
<img width="1736" height="418" alt="image" src="https://github.com/user-attachments/assets/52fb571c-ce91-473f-8c11-249e09e0c622" />

_Figura 3.2_

Otras técnicas de modulación que utilicen el mismo principio que PSK pueden ser:

* Binary Phase Shift Keying (BPSK)
* Quadrature Phase Shift Keying (QPSK)
* 8-PSK, 16-PSK, etc.
* Differential Phase Shift Keying (DPSK)
* Offset Phase Shift Keying (OPSK)

### Bit Error Rate
El Bit Error Rate es la tasa de bits erróneos recibidos, es decir, la cantidad de bits recibidos que difieren de los bits enviados en la totalidad del mensaje.
De las técnicas anteriores, la más robusta respecto al BER es la modulación BPSK, ya que al utilizar solo dos símbolos con fases opuestas, es decir con gran separación, se consigue gran resistencia al ruido del canal y es más fácil diferenciar los símbolos entre sí.

## 4) 

### Cisco Packet Tracer

A continuación instalaremos y construiremos una red simple en Packet Tracer. incluiremos dos computadoras y un router siguiendo el siguiente esquema:

<img width="1031" height="472" alt="image" src="https://github.com/user-attachments/assets/f7863294-a4d4-4045-83f3-b4f30e295099" />

_Figura 4.1_

El router opera con una frecuencia de 2.412 GHz, la región del espectro electromagnético que le corresponde son microondas dentro del espectro radioeléctrico y opera en la banda de 2.4 GHz

<img width="1669" height="808" alt="image" src="https://github.com/user-attachments/assets/3b53cff8-abfe-4b92-bcbc-352c282040f7" />

_Figura 4.2_

Direcciones IP de PC y laptop

<img width="1919" height="923" alt="image" src="https://github.com/user-attachments/assets/a4aaadc6-557d-4a2f-95d8-aa2198f8a3eb" />

_Figura 4.3_

Conexion de la red

<img width="1666" height="804" alt="image" src="https://github.com/user-attachments/assets/812db299-3e13-49ac-8146-e97d7c9b11af" />

_Figura 4.4_

Ping y traceroute entre PC y laptop

<img width="701" height="718" alt="image" src="https://github.com/user-attachments/assets/2f52389e-ae9f-4ab8-b940-dbcf613cd74f" />

_Figura 4.5_

<img width="1886" height="811" alt="image" src="https://github.com/user-attachments/assets/eaf7697c-b5f8-4d68-be38-90c6313b2fbf" />

_Figura 4.6_

Se puede ver que a medida que se la laptop se aleja del router y sale de la oficina, la señal del router pierde intensidad llegando a ser imposible la conexión

<img width="1179" height="360" alt="image" src="https://github.com/user-attachments/assets/6ec58f73-cd53-47fb-9e09-1cc6d0648442" />

_Figura 4.7_

Esto se ve reflejado en una disminución de las tasas de envío y recepción bajando de 300 Mbps cerca del router hasta 54 Mbps fuera de la oficina
