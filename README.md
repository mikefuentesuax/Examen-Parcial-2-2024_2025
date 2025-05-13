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
