# Examen-Parcial-2-2024_2025
https://github.com/mikefuentesuax/Examen-Parcial-2-2024_2025.git

# Parte I – Misiones de Conocimiento Teórico

## Misión 1: Reconexión en la Base Eco (Hoth) – Direccionamiento IP y Subredes

**Red Base:** 172.16.0.0/24

* **Comando Central:** ~50 hosts
* **Defensa Perimetral:** ~30 hosts
* **Centro Médico:** ~20 hosts
* **Hangar y Taller:** ~14 hosts
* **Enlace Troncal:** Necesita una subred para este enlace.

**Asignación de Subredes:**

| Departamento          | Dirección de Red | Máscara de Subred (/xx) | Hosts Útiles | Rango de Hosts         |
| :-------------------- | :--------------- | :--------------------- | :----------- | :--------------------- |
| Comando Central       | 172.16.0.0       | /26                   | 62           | 172.16.0.1 - 172.16.0.62  |
| Defensa Perimetral    | 172.16.0.64      | /27                   | 30           | 172.16.0.65 - 172.16.0.94  |
| Centro Médico         | 172.16.0.96      | /27                   | 30           | 172.16.0.97 - 172.16.0.126 |
| Hangar y Taller       | 172.16.0.128     | /28                   | 14           | 172.16.0.129 - 172.16.0.142 |
| Enlace Troncal        | 172.16.0.144     | /30                   | 2            | 172.16.0.145 - 172.16.0.146 |

---

## Misión 2: Sabiduría de Yoda – Algoritmos de Enrutamiento y Rutas

**Enrutamiento Estático:**

Son rutas ya predefinidas y configuradas manualmente por el administrador de la red. 

* **Ventajas:**
    * Seguridad ya que cuenta con un control total  y simplificidad para redes pequeñas.
* **Desventajas:**
    * No se puede adaptar a cambios de red grandes.

**Enrutamiento Dinámico:**

Se adapta automaticamente a las rutas según el estado de la red.

* **Ventajas:**
    * Se ajusta automaticamente.
    * Optimimza el uso de la red.
* **Inconvenientes:**
    * Requiere mayor uso de recursos.
    * Riesgp en la seguridad si no se controla de la forma correcta.

**Protocolos de Enrutamiento Dinámico: Vector de Distancia vs. Estado de Enlace**

Un ejemplo de protocolo de enrutamiento dinámico es el **RIP**. En este protocolo cada router informa del número de saltos a sus vecinos.

La diferencia es la información que comparten y cómo toman decisiones de enrutamiento:

* **Vector de Distancia**: Cada router informa a sus vecinos de la distancia a cada destino. Tiene una visión limitada de la red y una convergencia más lenta.

* **Estado de Enlace**: Cada router comparte información sobre sus enlaces directos, y todos los routers construyen un mapa completo de la red. Esto permite una convergencia rápida y rutas más eficientes, aunque a costa de un mayor uso de memoria y CPU.

En un entorno de enrutamiento estático, si un nodo o enlace cae, las rutas se interrumpen y es necesario reconfigurar manualmente las rutas afectadas.

En una red con enrutamiento dinámico, los protocolos detectan automáticamente el fallo y recalculan nuevas rutas, asegurando la continuidad del servicio.

## Misión 3: Los Nombres del Holonet – DNS y Resolución de Nombres

El DNS actúa como un directorio, traduciendo los nombres a las direcciones que los ordenadores necesitan.

1.  **La Petición:** Cuando un técnico rebelde intenta acceder a "holonet.rebelion.org", su computadora no sabe dónde está ese sitio. Envía una petición a un servidor DNS, preguntando: "¿Cuál es la dirección IP de holonet.rebelion.org?".
2.  **El Servidor DNS:** Este servidor es como un bibliotecario galáctico, especializado en buscar direcciones. Si el servidor DNS conoce la respuesta (porque la tiene en su "catálogo" o la ha preguntado recientemente), la envía de vuelta a la computadora del técnico.
3.  **Los Registros DNS:** El "catálogo" del servidor DNS está lleno de registros. Un registro **A** es el más común, y asocia un nombre de dominio (como "holonet.rebelion.org") con una dirección IP (por ejemplo, 192.168.1.10). Hay otros tipos de registros (como MX para correo electrónico, CNAME para alias, etc.), pero el registro A es crucial para la navegación web.
4.  **La Respuesta:** El servidor DNS envía la dirección IP (192.168.1.10) a la computadora del técnico.
5.  **La Conexión:** Ahora la computadora sabe a dónde ir y puede conectarse al servidor web de "holonet.rebelion.org".


* El técnico escribe "holonet.rebelion.org" en su navegador.
* La computadora pregunta a un servidor DNS: "¿Cuál es la IP de holonet.rebelion.org?".
* El servidor DNS responde: "192.168.1.10".
* La computadora se conecta a 192.168.1.10.

**La Importancia del DNS:**

* **Facilidad de Uso:** Permite a los usuarios recordar nombres en lugar de números complejos.
* **Flexibilidad:** Si la dirección IP de un servidor cambia, solo necesitamos actualizar el registro DNS. Los usuarios seguirán usando el mismo nombre.
* **Organización:** El DNS está organizado jerárquicamente, como un árbol, lo que permite gestionar millones de nombres de dominio de forma eficiente.

Si el servidor DNS rebelde no está disponible, es como si el directorio telefónico galáctico desapareciera.

* **Pérdida de Comunicación:** Lois ordenadores no podrán traducir los nombres de dominio a direcciones IP.
* **Sitios Web Inaccesibles:** Los técnicos no podrán acceder a sitios web usando sus nombres.
* **Interrupción de Servicios:** Muchos servicios dependen del DNS.

## Misión 4: “Es una trampa… de protocolos!” – TCP vs UDP en las transmisiones

**Características de TCP**
Es un protocolo orientado a la conexión, por lo cual establece un enlace entre el emisor y receptor. También garantiza que los datos lleguen en orden correcto y sin errores. Es más confiable pero consume más recurso.


**Consideraciones del UDP**
Adecuado para aplicaciones que requieren alta confiabilidad y precisión, como navegación web, correo electrónico, transferencia de archivos y acceso remoto. TCP garantiza que los datos se entreguen completa y correctamente, y maneja la congestión y el control de flujo para evitar la sobrecarga de la red. TCP también proporciona funciones de seguridad, como cifrado y autenticación, para proteger los datos del acceso o la modificación no autorizados.


**Características del UDP**
UDP es un protocolo sin conexión,  no crea ni mantiene ninguna conexión entre el emisor y el receptor. UDP simplemente envía los datos como paquetes, o datagramas, sin verificar ni garantizar su entrega, orden o integridad. UDP es rápido y eficiente, pero también tiene un mayor riesgo de perder, duplicar o corromper datos.


**Consideraciones del TCP**
UDP es adecuado para aplicaciones que requieren baja latencia y alto rendimiento, como streaming, juegos, voz sobre IP y videoconferencias. UDP no agrega ningún encabezado o proceso adicional a los datos, y permite que el remitente controle la velocidad y el tamaño de los paquetes. UDP también admite multidifusión y difusión, lo que permite al remitente transmitir datos a varios receptores a la vez.


## Misión 5: Comunicación Segura o Lado Oscuro – Criptografía y Seguridad de la Red

La victoria rebelde depende de que sus comunicaciones permanezcan secretas.

**Cifrado Simétrico vs. Cifrado Asimétrico:**

La clave para la seguridad reside en el uso de claves secretas para cifrar nuestros mensajes, de manera que solo aquellos con la clave correcta puedan descifrarlos. Existen dos métodos principales para esto:

* **Cifrado Simétrico:** Se utiliza la misma clave secreta tanto para cifrar como para descifrar el mensaje.

    * **Funcionamiento:** Una clave compartida se usa para codificar y decodificar la información.
    * **Ventajas:** Generalmente más rápido y requiere menos poder computacional.
    * **Ejemplo en la Narrativa:** Cuando Leia y Luke comparten una frase clave secreta para cifrar sus holomensajes, ese es un ejemplo de **cifrado simétrico**.

* **Cifrado Asimétrico (o de Clave Pública/Privada):** Cada participante tiene dos claves: una **clave pública** (que puede compartir) y una **clave privada** (que debe mantener en secreto).

    * **Funcionamiento:** Un mensaje cifrado con la clave pública solo puede descifrarse con la clave privada correspondiente.
    * **Ventajas:** Permite la comunicación segura sin intercambio previo de claves y facilita la autenticación.
    * **Ejemplo en la Narrativa:** Si la Alianza quiere enviar un mensaje a un nuevo aliado sin haber intercambiado una clave secreta previamente, puede usar la **clave pública** del aliado para cifrar el mensaje, el cual solo podrá ser leído con la **clave privada** del aliado.

**Importancia de la Autenticación y el No Repudio:**

* **Autenticación:** Asegura que el mensaje realmente proviene de quien dice ser (mediante **firmas digitales** creadas con la clave privada del emisor y verificadas con su clave pública).
* **No Repudio:** Evita que el emisor niegue haber enviado el mensaje (también logrado con **firmas digitales**).

**La Crucial Importancia de Protocolos Seguros (SSH vs. Telnet):**

* **Telnet:** Envía toda la información en texto plano, incluyendo credenciales, lo que lo hace inseguro para la administración remota.
* **SSH (Secure Shell):** Cifra toda la comunicación entre el administrador y el equipo remoto, protegiendo las credenciales y los datos transmitidos. Utilizar SSH es crucial al administrar remotamente los equipos de la red rebelde.

Implementando estas medidas, podemos construir una red de comunicaciones rebelde que sea resistente a la escucha y manipulación por parte del lado oscuro.

