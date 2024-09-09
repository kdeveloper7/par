# **Unidad 0: Conceptos previos**


## **Objetivos**
- Aprender a operar con los diferentes sistemas de numeración.
- Clasificar y caracterizar los canales de transmisión.
- Entender los distintos tipos de direccionamiento utilizados en una red.
- Configurar y gestionar los parámetros TCP/IP en los dispositivos de una red.
- Aplicar la división de subredes a partir de una dirección de red.
- Instalar y manejar una herramienta de simulación  de redes de ámbito global.

## **Mapa conceptual**
<img src="../images/mapa-conceptual.png">

### Glosario

!!! info "Glosario de términos"

    **APIPA**: Del inglés, *Automatic Private Internet Protocol Addressing*, siglas que hacen alusión a direccionamiento privado automático del protocolo de Internet. Protocolo utilizado para la autoconfiguración de dispositivos.

    **CNA**: Del inglés, *Cisco Networking Academy*, programa educativo sin ánimo de lucro cuyo objetivo es contribuir a la preparación de estudiantes en el diseño, configuración y mantenimiento de redes, a través de uno de los modelos online más avanzados.

    **DHCP**: Siglas en inglés relativas al protocolo de configuración dinámica de *host*. Protocolo que se instala en el servidor, utilizado para asignar los parámetros TCP/IP a los dispositivos clientes de red conectados.

    **DNS**: Hace referencia al servicio o sistema de nombres de dominio (*Domain Name System*) y es utilizado para asociar las direcciones IP con sus correspondientes nombres de dominio.

    **Hexteto**: Término utilizado para referirse al conjunto de 16 bits o bien al conjunto de cuatro caracteres hexadecimales consecutivos.

    **ISP**: Del inglés, *Internet Service Provider*. Término utilizado para identificar a las compañías que proporcionan acceso a Internet.

    **Nibble**: Término utilizado para referirse al conjunto de cuatro dígitos binarios.

    **Octeto**: Término utilizado para referirse al conjunto de 8 bits. También es denominado *Byte*.

    **Subnetting**: Término que hace referencia a la subdivisión de una red en varias subredes. Siglas del inglés *Transfer Control Protocol/Internet Protocol*, que hacen mención a la arquitectura de red del mismo nombre.

## **0.1. Sistemas de numeración: binario, octal, decimal y hexadecimal**

En el contexto tecnológico de la informática y las telecomunicaciones, al igual que en tantos otros, se hace evidente la necesidad de utilizar sistemas de representación. Los ordenadores y las redes de telecomunicaciones fundamentan dicha representación en cuatro sistemas: binario, octal, decimal y hexadecimal. Todos ellos disponen de su correspondiente expresión polinómica para representar cualquier magnitud en su equivalente decimal, tal y como se muestra en el cuadro siguiente:

  **Cuadro 0.1** 

| **Sistema**  | **Expresiones polinómicas**                                                                   |
|--------------|----------------------------------------------------------------------------------------------|
| **Binario**  | N₁₀ = aₙ . 2ⁿ + aₙ₋₁ . 2ⁿ⁻¹ + ... + a₁ . 2¹ + a₀ . 2⁰ + ...                                |
| **Octal**    | N₁₀ = aₙ . 8ⁿ + aₙ₋₁ . 8ⁿ⁻¹ + ... + a₁ . 8¹ + a₀ . 8⁰ + ...                                |
| **Decimal**  | N₁₀ = aₙ . 10ⁿ + aₙ₋₁ . 10ⁿ⁻¹ + ... + a₁ . 10¹ + a₀ . 10⁰ + ...                            |
| **Hexadecimal**| N₁₀ = aₙ . 16ⁿ + aₙ₋₁ . 16ⁿ⁻¹ + ... + a₁ . 16¹ + a₀ . 16⁰ + ...                           |

Así, podemos representar cualquier número en base binaria, octal, decimal o hexadecimal en su forma polinómica exponencial. 

Por ejemplo:

- 1101₂ = 1 . 2³ + 1 . 2² + 0 . 2¹ + 1 . 2⁰ 
- 4076₈ = 4 . 8³ + 0 . 8² + 7 . 8¹ + 6 . 8⁰ 
- 9143₁₀ = 9 . 10³ + 1 . 10² + 4 . 10¹ + 3 . 10⁰ 
- 127FA₁₆ = 1 . 16³ + 2 . 16² + 7 . 16¹ + 15 . 16⁰ 

Cualquier número puede ser representado en cada uno de los sistemas, utilizando para ello los correspondientes símbolos de representación propios (por ejemplo, para el sistema binario se utilizan dos símbolos, el 0 y el 1, mientras que para el sistema octal se utilizan los símbolos 0, 1, 2, 3, 4, 5, 6 y 7).

## **Cuadro 0.2 - Equivalencias numéricas entre sistemas**

| **Hexadecimal** | **Decimal** | **Octal** | **Binario** |
|-----------------|-------------|-----------|-------------|
| 0               | 0           | 0         | 0000        |
| 1               | 1           | 1         | 0001        |
| 2               | 2           | 2         | 0010        |
| 3               | 3           | 3         | 0011        |
| 4               | 4           | 4         | 0100        |
| 5               | 5           | 5         | 0101        |
| 6               | 6           | 6         | 0110        |
| 7               | 7           | 7         | 0111        |
| 8               | 8           | 10        | 1000        |
| 9               | 9           | 11        | 1001        |
| A               | 10          | 12        | 1010        |
| B               | 11          | 13        | 1011        |
| C               | 12          | 14        | 1100        |
| D               | 13          | 15        | 1101        |
| E               | 14          | 16        | 1110        |
| F               | 15          | 17        | 1111        |

Es muy importante saber operar y transformar números entre los diferentes sistemas. Para ello, resulta muy útil manejar con soltura la equivalencia mostrada en el cuadro 1.3, que representa el valor decimal de cada uno de los bits de un octeto, según su peso.

## **Cuadro 0.3 - Valores decimales de la posición de cada bit**

| 2⁷  | 2⁶  | 2⁵  | 2⁴  | 2³  | 2²  | 2¹  | 2⁰  |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |

Por ejemplo:

<img src="../images/conv1.png">


<img src="../images/conversion-d-b.png">

El número 10101001₂ (en base 2) equivale al número 251₈ (en base octal):

- 10101001₂ → 251 (se agrupan de 3 en 3 dígitos de derecha a izquierda)

El número 10101001₂ (en base 2) equivale al número A9₁₆ (en base hexadecimal):

- 10101001₂ → A9 (se agrupan de 4 en 4 dígitos de derecha a izquierda)

El número 512₈ (en base 8) equivale al número 14A₁₆ (en base hexadecimal):

- 512₈ → 101001010₂ → 14A₁₆

---

!!! note "Actividad propuesta 0.1"
    **Completa la siguiente tabla con los valores adecuados**:

    | **Binario**    | **Octal** | **Decimal** | **Hexadecimal** |
    |----------------|-----------|-------------|-----------------|
    | 11011001       |           | 267         |                 |
    |                | 267       | 129         |                 |
    |                |           |             | FC              |

!!! info "Toma nota"
    Para transformar los números del formato octal al hexadecimal o viceversa se debe pasar previamente al formato decimal o binario.

## **0.2. Canales de transmisión de datos**

Un canal de transmisión de datos es el camino a través del cual viaja la información entre un emisor y un receptor. Estos datos pueden propagarse sobre medios guiados (por ejemplo, los cables de par trenzado) o sobre medios no guiados (por ejemplo, las ondas de radio).

### **0.2.1. Transmisión de datos analógica y digital**

La transmisión de información entre dos o más puntos puede realizarse utilizando infinidad de tecnologías, pero todas ellas se fundamentan en la transmisión de dos tipos concretos de señales: analógicas o digitales. Estas señales serán las que transporten los datos propiamente dichos, es decir, los datos que se envían son siempre información digital que será transmitida a través de un medio, utilizando para ello, o bien una señal analógica, o bien una señal digital.

<div style="border: 1px solid #ddd; padding: 10px; border-radius: 8px; background-color: #f9f9f9; text-align: center;">

  <div style="display: flex; justify-content: space-around; align-items: center;">

    <div>
      <img src="../images/analogica.png" alt="Señal analógica" style="width: 300px;">
    </div>

    <div>
      <img src="../images/digital.png" alt="Señal digital" style="width: 300px;">
    </div>

  </div>

  <div style="margin-top: 10px; font-weight: bold; font-size: 1.2em;">
    Figura 0.1 - Gráficas de señal analógica y digital.
  </div>

</div>



**Por ejemplo:**

La red telefónica básica (RTB) o red telefónica conmutada (RTC) es un claro ejemplo de sistema analógico, el cual ha sido ampliamente utilizado, y todavía lo sigue siendo, como medio de transmisión de voz.

Las actuales infraestructuras de redes de fibra óptica que dan soporte para el acceso a Internet, como por ejemplo, Movistar, Jazztel, etc., representan sistemas digitales, y en algunos de los casos, lo son totalmente de extremo a extremo (FTTH – *Fiber To The Home*).

### **0.2.2. Características de los canales de transmisión**

Existen numerosas clasificaciones o taxonomías de los canales o medios de transmisión en función de las características bajo las que se realice dicho estudio. Algunos de los parámetros o características más importantes son:

1. **Velocidad de transmisión**. Se mide en bits por segundo (bps) o múltiplos de este (Kbps, Mbps, etc.) y permite cuantificar la velocidad a la que pueden transmitirse los datos a través de un canal. Por ejemplo, una red FastEthernet tiene una velocidad de transmisión máxima de 100 Mbps.

2. **Ancho de banda**. También conocido como banda de paso, suele expresarse en hercios (Hz) y define el conjunto de frecuencias que son capaces de transmitirse sobre un canal. Por ejemplo, habitualmente, las bandas de frecuencia más utilizadas en las redes wifi son la de 2,4 GHz y la de 5 GHz.

3. **Ruido**. Es el conjunto de fenómenos o interferencias que pueden afectar al canal de transmisión. Puede ser causado por factores externos al canal o ser inherentes al mismo. Por ejemplo, la diafonía que se produce en un canal por la proximidad de otro canal.

4. **Distancia máxima**. Suele medirse en metros (m) o kilómetros (km) y hace referencia a la distancia máxima que es capaz de alcanzar la señal transmitida sin perder su capacidad de ser interpretada correctamente por el receptor. Por ejemplo, en una red Ethernet la distancia máxima del cable de par trenzado que puede utilizarse entre dos nodos es de 100 m.

---

## **0.3. Direccionamiento físico y lógico de una red**

De la misma forma que es utilizado el número de bastidor de un automóvil para poder identificarlo y diferenciarlo de todos los demás, es necesario utilizar un mecanismo de identificación, para poder identificar de forma única los diferentes dispositivos dentro de una red informática. Este mecanismo recibe el nombre de **direccionamiento**.

De forma general, podemos diferenciar dos tipos de direcciones en el entorno de una red de ordenadores: las direcciones físicas y las direcciones lógicas. Para una mejor comprensión de estos conceptos conviene basarse en la arquitectura de red TCP/IP, mostrada en el cuadro **0.4**, la más ampliamente utilizada en las redes a nivel mundial.

---

### **Cuadro 0.4 - Niveles de la arquitectura TCP/IP con su direccionamiento**

| **Nivel o capa**         | **Sistema de direccionamiento**  | **Ejemplos**            |
|--------------------------|----------------------------------|-------------------------|
| Aplicación               | Protocolos de aplicación         | http, ftp, etc.         |
| Transporte               | Puertos de acceso                | 80, 21, etc.            |
| Internet                 | Direcciones lógicas              | IPv4, IPv6              |
| Acceso a la red          | Direcciones físicas              | MAC                     |


### **0.3.1. Direccionamiento físico (MAC)**

La dirección física o **MAC** (*Media Access Control*) es un identificador único de 48 bits. Está compuesto por 6 grupos de 2 dígitos hexadecimales, conocidos como *nibbles*, y se representa en formato hexadecimal. Este tipo de dirección es válida únicamente en redes locales (LAN), donde se utiliza para identificar dispositivos que están conectados a la misma red. Si se quiere comunicar con un dispositivo fuera de la red local, es necesario usar un direccionamiento lógico.

El formato estándar de una dirección MAC es:

AA:BB:CC:DD:EE  


Los primeros tres bloques (**AA:BB:CC**) identifican al fabricante del dispositivo, mientras que los últimos tres bloques (**DD:EE:FF**) contienen el número de serie único de la tarjeta de red. Esta dirección es asignada por el fabricante y no puede ser duplicada entre dispositivos. 

Para visualizar la dirección MAC de un dispositivo, puedes utilizar el comando en Windows: 
```javascript
ipconfig /all
```  
o en Linux:
```js
ifconfig
```
Estos comandos muestran la información de la red, incluyendo la dirección física del dispositivo.

![Señal analógica](../images/mac.png)
**Figura 0.2 Visualización en consola de dirección física o MAC.**


### **0.3.2. Direccionamiento lógico (IPv4)**

El direccionamiento lógico es un método que asigna un identificador único a la interfaz de red o tarjeta de red de un dispositivo. Este identificador puede utilizarse tanto en redes locales como en redes globales, permitiendo que los dispositivos se comuniquen entre sí, ya sea dentro de la misma red local o fuera de ella.

La dirección **IPv4** es una dirección lógica compuesta por 32 bits, organizados en 4 grupos de 8 bits cada uno, separados por puntos. Cada uno de estos grupos se representa en formato decimal. Esta dirección se divide en dos partes principales: una parte identifica la red, mientras que la otra parte se refiere al dispositivo específico dentro de esa red (el *host*). Más adelante en este capítulo se explicará en detalle esta división. El formato típico de una dirección IPv4 es el siguiente:

**W.X.Y.Z (10**

De manera similar a como se hace con las direcciones físicas, es bastante sencillo determinar cuál es la dirección lógica de la interfaz de red o **NIC** (*Network Interface Controller*). La figura 0.3 muestra un ejemplo.

<div style="border: 1px solid #ddd; padding: 10px; border-radius: 8px; background-color: #f9f9f9; text-align: center;">

  <div style="display: flex; justify-content: space-around; align-items: center;">

    <div>
      <img src="../images/ipv4.png" alt="Señal analógica" ;">
    </div>

  </div>

  <div style="margin-top: 10px; font-weight: bold; font-size: 1.2em;">
    Figura 0.3 - Visualización dirección lógica IPv4.
  </div>

</div>

En cuanto a las partes funcionales que conforman una dirección **IPv4** (recordemos que tiene dos partes: la parte de red y la parte del *host*), es crucial señalar que su principal función es identificar la red o subred a la que pertenece un dispositivo en particular.

El direccionamiento **IPv4** se organiza en diferentes clases, lo que permite establecer rangos de direcciones específicas. Estas clases facilitan el diseño y análisis de redes de distinta magnitud. Así, el tipo de clase que se utilice dependerá del tipo de red y la cantidad de dispositivos que vayan a formar parte de dicha red.

Dentro de cada clase de direcciones IPv4, se establecen subrangos de direcciones, lo que da lugar a los **rangos de direcciones públicas y privadas**. Las direcciones públicas son asignadas a dispositivos que necesitan estar directamente accesibles en Internet, mientras que las direcciones privadas se aplican a dispositivos conectados en una red interna y que no requieren acceso directo a Internet. El cuadro 0.5 muestra los rangos de direcciones públicas y privadas en las tres primeras clases de IPv4.

---

### **Cuadro 0.5 - Rangos de direcciones IPv4 públicas y privadas**

| **Clase** | **Direcciones públicas**        | **Direcciones privadas**           | **Máscara de red**      |
|-----------|---------------------------------|------------------------------------|-------------------------|
| **A**     | 1.0.0.1 - 126.255.255.254       | 10.0.0.1 - 10.255.255.254          | 255.0.0.0               |
| **B**     | 128.0.0.1 - 191.255.255.254     | 172.16.0.1 - 172.31.255.254        | 255.255.0.0             |
| **C**     | 192.0.0.1 - 223.255.255.254     | 192.168.0.1 - 192.168.255.254      | 255.255.255.0           |

---

En el diseño de redes utilizando **IPv4**, es esencial tener en cuenta cuántos dispositivos van a formar parte de la red. Como se explicó previamente, una dirección IPv4 está formada por dos partes: una que identifica la red y otra que identifica el dispositivo dentro de esa red. Esta organización facilita la asignación de direcciones y ayuda a gestionar correctamente el tráfico de red.

El concepto de **máscara de red** se abordará más adelante en la sección 0.5.1. El cuadro 0.6 muestra la relación entre las clases IPv4 y sus partes funcionales.

---

### **Cuadro 0.6 - Partes funcionales de una dirección IPv4: parte de red y parte de host**

| **Clase** | **Parte funcional**        | **Número de redes**         | **Número de hosts**        |
|-----------|----------------------------|-----------------------------|----------------------------|
| **A**     | red.host.host.host          | 2⁷ - 2 = 128                | 2²⁴ - 2 = 16777214          |
| **B**     | red.red.host.host           | 2¹⁴ = 16384                 | 2¹⁶ - 2 = 65534             |
| **C**     | red.red.red.host            | 2²¹ = 2097152               | 2⁸ - 2 = 254                |

---

!!! info "Recuerda"
    Para calcular cuántos **hosts** pueden conectarse en una red determinada, debes tener en cuenta el número de bits disponibles para los hosts y restar dos de ese valor. Esto se debe a que la primera dirección, que solo contiene ceros, se reserva para identificar la red, y la última, compuesta de unos, se reserva para fines especiales.

---

Por ejemplo:

Si tenemos la dirección IP **195.214.12.0** con la máscara **255.255.255.0**, se podrán direccionar los **hosts** desde **195.214.12.1** hasta **195.214.12.254**. Ten en cuenta que las direcciones que terminan en 0 identifican la red, mientras que la que termina en 255 está reservada para otras funciones.

---

!!! note "Actividad propuesta 0.2"
    Se te proporciona la configuración de una red doméstica. Debes asignar las direcciones TCP/IP a dos equipos cliente y un servidor, dentro del rango privado **192.168.1.0/24**. Recuerda asignar las primeras direcciones IP disponibles a los clientes y reservar la última IP para el **gateway**. Usa la dirección restante para el servidor, siguiendo una asignación descendente.

    ![Diagrama de la red doméstica](../images/act0-2.png)



Rellena la tabla siguiente con los parámteros TCP/IP correspondientes:


| **Equipo**     | **Dirección IPv4** | **Máscara de red** | **Gateway**    |
|----------------|--------------------|--------------------|----------------|
| Router casa    |                    |                    |                |
| Cliente 1      |                    |                    |                |
| Cliente 2      |                    |                    |                |
| Servidor       |                    |                    |                |



### **0.3.3. Direccionamiento lógico (IPv6)**

Las direcciones **IPv6** están formadas por 128 bits, que se agrupan en 8 bloques de 16 bits cada uno. Estos bloques suelen representarse en formato hexadecimal y están separados por dos puntos (:). Un ejemplo de una dirección IPv6 sería:

8888:9999:AAAA:BBBB:CCCC:DDDD:EEEE (16

Las direcciones IPv6 se clasifican en tres tipos principales:

1. **Unicast**: Se utiliza para identificar una única interfaz de red en un nodo. Cuando un paquete se envía a una dirección Unicast, solo ese nodo lo recibe.
2. **Multicast**: Se utiliza para enviar un paquete a un grupo de nodos. Todos los dispositivos del grupo recibirán el paquete al mismo tiempo.
3. **Anycast**: Similar a Multicast, pero en este caso, el paquete lo recibe el nodo más cercano al remitente, es decir, el nodo que pueda ofrecer la mejor ruta.

Además de estos tipos, existen **subtipos de direcciones IPv6**, que son específicos para ciertos usos. Los subtipos más importantes pertenecen a las direcciones **Unicast** y son:

- **Global**: Son las direcciones que se utilizan para la conexión a Internet, equivalentes a las direcciones públicas en IPv4.
- **Enlace Local (Link-Local)**: Se usan solo dentro de una red local y no pueden ser enrutadas hacia Internet. Estas direcciones permiten la autoconfiguración de los nodos, y son equivalentes al protocolo **APIPA** en IPv4.
- **Sitio Local (Site-Local o Unique-Local)**: Se utilizan en redes locales, aunque pueden ser enrutadas dentro de ese sitio. Sin embargo, no pueden ser enrutadas hacia Internet. Son equivalentes a las direcciones privadas utilizadas en IPv4.

---

### Resumen de las Direcciones IPv6

- **Unicast**: Envía datos a un solo nodo.
- **Multicast**: Envía datos a varios nodos simultáneamente.
- **Anycast**: Envía datos al nodo más cercano al remitente.

Los subtipos como **Global**, **Link-Local** y **Site-Local** definen cómo se manejan las direcciones IPv6 en redes locales e Internet.

<div style="border: 1px solid #ddd; padding: 10px; border-radius: 8px; background-color: #f9f9f9; text-align: center;">

  <div style="display: flex; justify-content: space-around; align-items: center;">

    <div>
      <img src="../images/ipv6.png" alt="ipv6" ;">
    </div>

  </div>

  <div style="margin-top: 10px; font-weight: bold; font-size: 1.2em;">
    Figura 0.4 - Clasificación de las IPv6.
  </div>

</div>


Hay que tener en cuenta que en las direcciones **IPv6** también se utilizan prefijos y rangos concretos según el tipo y subtipo de dirección utilizada. De forma general, se establece un primer prefijo de **48 bits** (los tres primeros hextetos) denominado **prefijo de sitio**, y un segundo prefijo de **16 bits** (cuarto hexteto) llamado **prefijo de subred**, dejando los últimos 64 bits (últimos cuatro hextetos) para el identificador de la interfaz.

---

!!! info "¡Sabías que...!"
    Actualmente están operativos los dos protocolos de direccionamiento, **IPv4** e **IPv6**, aunque gradualmente se irá utilizando con mayor frecuencia el segundo. Además, el direccionamiento **broadcast** no existe en IPv6.

---

Por último, es importante saber que en la asignación automática de dirección **IPv6** que se utiliza para el tipo **Unicast**, subtipo **Enlace-Local**, se sigue lo especificado en el **protocolo EUI-64**, el cual permite calcular el identificador de interfaz (los últimos 64 bits) de la dirección IPv6, a partir de la dirección física (MAC) de la interfaz de red, realizando dos sencillas operaciones:

1. Primero, se añade el hexteto **FFFE** justo en la parte central de la dirección MAC.
2. Luego, se invierte el bit 7 de la dirección física (MAC), que consta de solo 48 bits.

De esta forma, se necesitan 16 bits más (un hexteto) para completar los 64 bits necesarios del identificador de interfaz en formato IPv6.

---

!!! note "Actividad propuesta 0.3"
    La representación de direcciones IPv6 supone una cadena excesivamente larga de caracteres hexadecimales. ¿Sabes si existe alguna forma o método de abreviación para este tipo de direcciones IP que permita escribirlas de forma más corta?

    En segundo lugar, se convierten los dos primeros caracteres hexadecimales, es decir, el primer octeto de la dirección física o MAC a código binario y, luego, se invierte el valor del 7° bit (empezando a contar por la izquierda).

Por ejemplo:

Transformación de la dirección física **00:E0:08:19:02:40**₁₆ en un identificador de interfaz IPv6 utilizando el protocolo EUI-64:

1. **Primer paso**, se insertan en la parte central los caracteres hexadecimales **FFFE**: 

00:E0:08:FF:FE:19:02:40₁₆


2. **Segundo paso**, se convierte a binario el primer octeto de la dirección física y se invierte el valor del 7° bit (empezando por la izquierda):

00000000₂:E0:08:FF:FE:19:02:40₁₆ 

s00000010₂:E0:08:FF:FE:19:02:40₁₆


3. Dando como resultado final el identificador de interfaz IPv6:

02:E0:08:FF:FE:19:02:40₁₆


---

!!! note "Actividad propuesta 0.4"
    Se desea configurar la siguiente red local utilizando direccionamiento IPv6. Para ello, deberán utilizarse dos direcciones de tipo Unicast en cada interfaz, que serán **global** y **link-local**. La IP **global** de red estará en el rango **2001:DB8:A:1::/64** y la **link-local** en el rango **FE80::/64**.
    
    Recuerda que es costumbre en el diseño asignar las primeras IP disponibles a los equipos cliente dejando la última IP disponible para el **gateway**, y sucesivamente, de forma descendente, para los equipos servidores, si los hubiera.

    ![Diagrama de la red doméstica](../images/act0-4.png)

 | **Equipo**  | **IPv6 global/máscara** | **IPv6 link-local** | **Gateway global/link-local** |
 |-------------|--------------------------|---------------------|-------------------------------|
 | Router      | ----                     | ----                | ----                          |
 | Cliente 1   |                           |                     |                               |
 | Cliente 2   |                           |                     |                               |


